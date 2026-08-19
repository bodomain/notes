	Good choice. OpenWork provides a native Linux desktop app, so on Debian the easiest approach is to use the **AppImage**. There is no official `.deb` package yet. ([OpenWork][1])

## 1. Install prerequisites

```bash
sudo apt update
sudo apt install -y fuse3 libfuse2t64 curl wget
```

On Debian 12 (Bookworm), if `libfuse2t64` doesn't exist:

```bash
sudo apt install libfuse2
```

---

## 2. Download OpenWork

Either download it from

[OpenWork Downloads](https://openworklabs.com/download?utm_source=chatgpt.com)

or directly from the terminal (replace the filename if a newer version exists):

```bash
mkdir -p ~/Applications
cd ~/Applications

wget https://github.com/OpenWorkLabs/openwork/releases/latest/download/OpenWork-x86_64.AppImage
```

If GitHub redirects differently, just download the AppImage from the website into `~/Applications`.

---

## 3. Make it executable

```bash
chmod +x ~/Applications/OpenWork*.AppImage
```

---

## 4. Run it

```bash
~/Applications/OpenWork*.AppImage
```

If you see a FUSE error:

```bash
./OpenWork*.AppImage --appimage-extract
cd squashfs-root
./AppRun
```

---

## 5. Optional: Create a launcher

Create

```bash
~/.local/share/applications/openwork.desktop
```

with

```ini
[Desktop Entry]
Name=OpenWork
Exec=/home/$USER/Applications/OpenWork-x86_64.AppImage
Icon=openwork
Type=Application
Categories=Development;
Terminal=false
```

Adjust the filename if necessary.

---

## 6. First start

OpenWork will ask you to:

* connect ChatGPT or another provider
* or add your own API keys (OpenAI, Anthropic, Gemini, etc.)
* create a workspace
* optionally install MCP servers and skills. ([OpenWork][2])

---

### Since I know your setup...

You already have:

* Debian
* VS Code
* Docker
* Codex/OpenCode
* Linux admin experience

I'd recommend using OpenWork primarily as an **MCP orchestration layer** rather than as another chat application. One of its strengths is packaging and sharing skills, MCP servers, and workflows that multiple AI clients can use. ([OpenWork][3])

If you're at the Debian terminal now, paste the output of:

```bash
cat /etc/debian_version
uname -a
```

and I'll tailor the installation for your exact Debian version (12 or 13).

[1]: https://openworklabs.com/download?utm_source=chatgpt.com "Download OpenWork — macOS, Windows, Linux"
[2]: https://openworklabs.com/docs/start-here/get-started?utm_source=chatgpt.com "Get started - OpenWork Docs"
[3]: https://openworklabs.com/?utm_source=chatgpt.com "OpenWork — Open source Claude Cowork alternative for teams"
