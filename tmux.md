# **Tmux Cheat Sheet** 💻

---

## **Tmux Sessions**

| Command                            | Description                           |
| :--------------------------------- | :------------------------------------ |
| `tmux`                             | Create a new session                  |
| `tmux new`                         | Create a new session                  |
| `tmux new-session`                 | Create a new session                  |
| `tmux new -s sessionname`          | Create a session with a specific name |
| `tmux a`                           | Attach to a session                   |
| `tmux att`                         | Attach to a session                   |
| `tmux attach`                      | Attach to a session                   |
| `tmux attach-session`              | Attach to a session                   |
| `tmux a -t sessionname`            | Attach to a specific session          |
| `tmux kill-ses`                    | Remove a session                      |
| `tmux kill-session -t sessionname` | Remove a session                      |
| `CTRL + B $`                       | Rename the current session            |
| `CTRL + B D`                       | Detach from the current session       |
| `CTRL + B )`                       | Go to the next session                |
| `CTRL + B (`                       | Go to the previous session            |

---

## **Tmux Windows** 🖼️

Windows are like **tabs** in a web browser. They exist within a session and occupy the entire screen space of that session.

| Command          | Description                   |
| :--------------- | :---------------------------- |
| `CTRL + B C`     | Create a new window           |
| `CTRL + B N`     | Move to the next window       |
| `CTRL + B P`     | Move to the previous window   |
| `CTRL + B L`     | Move to the last-used window  |
| `CTRL + B 0...9` | Select a window by its number |
| `CTRL + B '`     | Select a window by its name   |
| `CTRL + B .`     | Change the window's number    |
| `CTRL + B ,`     | Rename the current window     |
| `CTRL + B F`     | Search for windows            |
| `CTRL + B &`     | Kill the current window       |
| `CTRL + B W`     | List all windows              |

---

## **Tmux Panes**

Panes are sections of a window that have been split into multiple screens, similar to the individual panes of a real window. They allow you to view and interact with several shells at once within a single window.

| Command | Description |
| :--- | :--- |
| `CTRL + B %` | Split the pane **vertically** |
| `CTRL + B “` | Split the pane **horizontally** |
| `CTRL + B →` | Move to the pane on the right |
| `CTRL + B ←` | Move to the pane on the left |
| `CTRL + B ↑` | Move up to the pane above |
| `CTRL + B ↓` | Move down to the pane below |
| `CTRL + B O` | Go to the next pane |
| `CTRL + B ;` | Go to the last active pane |
| `CTRL + B }` | Move the current pane to the right |
| `CTRL + B {` | Move the current pane to the left |
| `CTRL + B !` | Convert the current pane into a new window |
| `CTRL + B X` | Kill the current pane |

---

## **Tmux Copy Mode** 📝

Copy mode lets you select text from the terminal output, copy it, and paste it.

### **Copy Mode Key Bindings**

| Command | Description |
| :--- | :--- |
| `CTRL + B [` | Enter copy mode |
| `CTRL + B ]` | Paste from the buffer |

### **Commands within Copy Mode**

| Command | Description |
| :--- | :--- |
| `space` | Start a selection |
| `enter` | Copy the selected text |
| `esc` | Clear the selection |
| `g` | Go to the top of the output |
| `G` | Go to the bottom of the output |
| `h` | Move the cursor left |
| `j` | Move the cursor down |
| `k` | Move the cursor up |
| `l` | Move the cursor right |
| `/` | Search for text |
| `#` | List paste buffers |
| `q` | Quit copy mode |