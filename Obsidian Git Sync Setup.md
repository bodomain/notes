# Obsidian Git sync setup

This note documents how the `~/notes` Obsidian vault is synchronized through GitHub, what was configured on the first Linux desktop, and how to reproduce the setup on another desktop.

## Overview

The vault is an ordinary Git repository:

- Local path: `~/notes`
- Branch: `main`
- Remote: `git@github.com:bodomain/notes.git`
- Sync tool inside Obsidian: **Git** (`obsidian-git`)
- Installed plugin version on the first desktop: `2.38.6`
- Automatic sync interval: 10 minutes while Obsidian is running
- Pull on Obsidian startup: enabled
- Sync strategy: commit local changes, pull with a merge, then push
- Automatic commit message: `vault sync: YYYY-MM-DD HH:mm:ss`

Git is used both for synchronization and version history. It is not live, simultaneous editing: let one device finish syncing before editing the same note on another device.

## What was changed on the first desktop

The Git community plugin was installed under:

```text
~/notes/.obsidian/plugins/obsidian-git/
├── data.json
├── main.js
├── manifest.json
└── styles.css
```

The plugin was added to `.obsidian/community-plugins.json`, which makes Obsidian enable it when the vault opens.

The following plugin behavior was configured:

| Setting | Value | Purpose |
|---|---:|---|
| Auto commit-and-sync interval | 10 minutes | Periodically commit, pull, and push |
| Pull on startup | Enabled | Fetch changes when Obsidian starts |
| Pull before push | Enabled | Incorporate remote commits before publishing local ones |
| Push disabled | No | Allow automatic pushes |
| Sync method | Merge | Match the repository's existing `pull.rebase=false` setting |
| Commit message | `vault sync: {{date}}` | Give automatic commits recognizable timestamps |
| Date format | `YYYY-MM-DD HH:mm:ss` | Produce readable timestamps |
| Error notices | Enabled | Make authentication and conflict failures visible |
| Status bar | Enabled | Show whether synchronization is healthy |
| Submodules | Disabled | This vault does not use them |

The plugin files and `data.json` are deliberately ignored by Git because `.gitignore` contains `.obsidian`. Existing Obsidian configuration files that were already tracked remain tracked, but newly installed plugin files remain local to each device. This has two useful consequences:

1. Every desktop must install and configure the Git plugin locally.
2. Device-local plugin data and credentials are not accidentally published.

In particular, these files were confirmed to remain ignored:

```text
.obsidian/plugins/obsidian-git/data.json
.obsidian/plugins/obsidian-local-rest-api/data.json
```

The original `.obsidian/community-plugins.json` was backed up on the first desktop at:

```text
/tmp/obsidian-git-backup-20260818/community-plugins.json
```

Files under `/tmp` are temporary and may disappear after a reboot, so Git history is the long-term recovery mechanism once the activation change has been committed.

## Set up another Linux, macOS, or Windows desktop

### 1. Install Git and Obsidian

Install native Git and the normal desktop version of Obsidian. On Linux, prefer an AppImage or a package with normal filesystem access. Sandboxed Snap or Flatpak installations can prevent the plugin from reaching Git, SSH, or the vault.

Verify Git:

```bash
git --version
```

### 2. Configure Git identity

Automatic commits need an author name and email:

```bash
git config --global user.name "YOUR NAME"
git config --global user.email "YOUR EMAIL"
```

Check the result:

```bash
git config --global --get user.name
git config --global --get user.email
```

### 3. Configure GitHub SSH access

Each desktop needs its own SSH key. Do not copy a private key between devices unless you intentionally manage keys that way.

If the device does not already have a GitHub-capable key:

```bash
ssh-keygen -t ed25519 -C "YOUR EMAIL"
```

Add the generated public key to GitHub under **Settings → SSH and GPG keys**. The public key normally lives at `~/.ssh/id_ed25519.pub`.

Test authentication:

```bash
ssh -T git@github.com
```

GitHub should recognize the account. A message saying that GitHub does not provide shell access is normal.

If the key has a passphrase, configure the operating system's SSH agent or keychain so Obsidian can use it. Otherwise automatic sync may pause for a passphrase prompt.

### 4. Clone the vault

If `~/notes` does not exist on the new device:

```bash
git clone git@github.com:bodomain/notes.git ~/notes
```

If the vault already exists as a clone, make sure it is clean and current:

```bash
git -C ~/notes status
git -C ~/notes pull
```

Do not overwrite an existing directory containing uncommitted notes. Commit or copy those notes somewhere safe before cloning or pulling.

### 5. Open the vault in Obsidian

In Obsidian, select **Open folder as vault** and choose `~/notes`.

If prompted, enable Community Plugins for this vault.

### 6. Install the Git community plugin

In Obsidian:

1. Open **Settings → Community plugins**.
2. Select **Browse**.
3. Search for **Git** by Vinzent.
4. Install it.
5. Enable it.

Installing through Obsidian is preferred because it obtains the current compatible release. The first desktop used version `2.38.6`; a newer stable version is fine unless it introduces a known regression.

### 7. Configure the plugin

Open **Settings → Git** and set:

```text
Commit message:                 vault sync: {{date}}
Automatic commit message:       vault sync: {{date}}
Commit date format:              YYYY-MM-DD HH:mm:ss
Auto commit-and-sync interval:   10 minutes
Pull on startup:                 enabled
Pull before push:                enabled
Disable push:                    disabled
Sync method:                     merge
Show error notices:              enabled
Show status bar:                 enabled
Update submodules:               disabled
```

Leave separate automatic pull and push intervals at `0`/disabled. The unified 10-minute commit-and-sync operation already performs the full sequence. Keeping only one timer avoids overlapping Git operations.

The effective workflow is:

```text
stage all changes → commit → pull/merge from origin/main → push to origin/main
```

### 8. Perform the first test

Before relying on automation, use Obsidian's command palette and run:

```text
Git: Commit-and-sync
```

Watch the status bar and notifications. Then verify in a terminal:

```bash
git -C ~/notes status --short --branch
git -C ~/notes log -3 --oneline --decorate
```

A healthy result has no modified files and reports that `main` is aligned with `origin/main`.

## Verify synchronization between two desktops

Use a temporary note rather than an important document:

1. On desktop A, create `sync-test.md` and add a unique sentence.
2. Run **Git: Commit-and-sync**, or wait up to 10 minutes.
3. Confirm the commit appears on GitHub.
4. Start Obsidian on desktop B and wait for the startup pull.
5. Confirm `sync-test.md` and its sentence appear.
6. Add a second sentence on desktop B and sync it.
7. Return to desktop A and confirm the second sentence arrives.
8. Delete the test note and let that deletion sync.

Repeat this test after changing SSH keys or reinstalling Git/Obsidian.

## Everyday workflow

Normally there is nothing to run manually:

1. Start Obsidian and let the startup pull finish.
2. Edit notes normally.
3. Keep Obsidian open long enough for the 10-minute commit-and-sync timer to run.
4. Before switching devices immediately, run **Git: Commit-and-sync** from the command palette and wait for success.
5. On the next device, start Obsidian and wait for its pull before editing.

The explicit command is important when moving quickly between computers because the timer may not have fired yet.

## Check synchronization from a terminal

Show the current state:

```bash
git -C ~/notes status --short --branch
```

Show recent automatic commits:

```bash
git -C ~/notes log -10 --oneline --decorate
```

Check whether the remote is reachable without modifying the vault:

```bash
git -C ~/notes ls-remote origin HEAD
```

Confirm the configured remote:

```bash
git -C ~/notes remote -v
```

The expected remote is:

```text
git@github.com:bodomain/notes.git
```

## Handling common failures

### Authentication or permission failure

Typical messages include `Permission denied (publickey)` or `Could not read from remote repository`.

1. Test `ssh -T git@github.com` in a terminal.
2. Confirm the device's public key is registered with the correct GitHub account.
3. Confirm the SSH agent has loaded the key.
4. Run `git -C ~/notes ls-remote origin HEAD`.
5. Retry **Git: Commit-and-sync** in Obsidian.

Do not replace the SSH URL with a GitHub password. GitHub does not accept account passwords for Git operations.

### The device was offline

The plugin may create a local commit but fail to pull or push. Once connectivity returns:

```bash
git -C ~/notes status --short --branch
```

Then run **Git: Commit-and-sync** again. Confirm the status bar reports success before switching devices.

### A merge conflict occurred

A conflict usually means two devices changed the same part of the same file before either received the other's commit.

1. Stop editing that note on all other devices.
2. Check the affected files:

   ```bash
   git -C ~/notes status
   ```

3. Open each conflicted Markdown file and look for markers:

   ```text
   <<<<<<< HEAD
   local text
   =======
   remote text
   >>>>>>> origin/main
   ```

4. Edit the file into the final desired version and remove all conflict markers.
5. Stage and commit the resolution:

   ```bash
   git -C ~/notes add --all
   git -C ~/notes commit -m "resolve vault sync conflict"
   git -C ~/notes push
   ```

6. Confirm `git -C ~/notes status` is clean.

Never use `git reset --hard` as a first response to a conflict: it can discard notes that exist only on the current device.

### Git reports `.git/index.lock`

First make sure no Git command and no Obsidian synchronization is still running. Close Obsidian and check again. Remove `.git/index.lock` only after confirming no Git process is active; deleting an active lock can corrupt an in-progress operation.

### Obsidian shows the plugin as missing

The activation list can travel through Git, but the plugin's actual files are ignored and device-local. Install **Git** from Community Plugins on that device, enable it, and apply the settings in this note.

## Security and backup notes

- Keep the GitHub repository private if the vault contains personal material.
- Never commit private SSH keys, GitHub tokens, REST API keys, or plugin credential files.
- Git synchronization is not a complete backup against every failure. Accidental deletion can also be committed and synchronized.
- GitHub history provides recovery for committed content, but consider an additional read-only or offline backup of `~/notes`.
- Do not run two independent live-sync tools against the same vault. Combining Git automation with Obsidian Sync, Syncthing, iCloud, Dropbox, or similar tools can create races and duplicate/conflicted files.

## Disable or remove the automation

To pause automatic synchronization without uninstalling anything:

1. Open **Settings → Git**.
2. Set the auto commit-and-sync interval to `0`.
3. Disable pull on startup.

Manual Git commands will continue to work.

To remove the plugin:

1. Perform one final **Git: Commit-and-sync**.
2. Disable **Git** under Community Plugins.
3. Uninstall it from Obsidian.
4. Verify the repository remains healthy with `git -C ~/notes status`.

Removing the plugin does not remove the repository or its history.

## Reference

- [Obsidian Git documentation](https://publish.obsidian.md/git-doc)
- [Obsidian Git source and releases](https://github.com/Vinzent03/obsidian-git)
- [Obsidian documentation: syncing notes](https://obsidian.md/help/sync-notes)

