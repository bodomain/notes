On Arch Linux with **Sway** (Wayland), you don’t have a traditional desktop environment audio control panel, so you’ll usually manage audio input/output through **PipeWire** (recommended), or **PulseAudio** (older).
Here are the main approaches:

---

## 1. Check your audio system

Most modern Arch installs use **PipeWire** with **WirePlumber** or **PipeWire Media Session**.

```bash
pactl info | grep 'Server Name'
```

* If it says *PulseAudio*, you’re running PipeWire with PulseAudio emulation (or pure PulseAudio).
* If it says *PipeWire*, then you’re on PipeWire.

---

## 2. Command-line tools

### List available input devices (sources):

```bash
pactl list sources short
```

### Set the default input device:

```bash
pactl set-default-source <SOURCE_NAME>
```

### Adjust input volume:

```bash
pactl set-source-volume <SOURCE_NAME> +10%   # increase by 10%
pactl set-source-volume <SOURCE_NAME> -10%   # decrease by 10%
pactl set-source-volume <SOURCE_NAME> 50%    # set to 50%
```

### Mute/unmute microphone:

```bash
pactl set-source-mute <SOURCE_NAME> 1   # mute
pactl set-source-mute <SOURCE_NAME> 0   # unmute
```

---

## 3. GUI tools

Even on Sway, you can launch GTK apps for easier control:

* **pavucontrol** → PulseAudio/pipewire volume control GUI
* **helvum** → Patchbay-style PipeWire connection manager
* **qpwgraph** → Graphical PipeWire patchbay (Qt-based)

Install them:

```bash
sudo pacman -S pavucontrol helvum qpwgraph
```

Launch them in Sway (e.g. with a keybind or terminal).

---

## 4. Integration with Sway

You can bind keys in `~/.config/sway/config` to control mic mute/unmute or switch sources. For example:

```bash
# Toggle microphone mute
bindsym $mod+Shift+m exec pactl set-source-mute @DEFAULT_SOURCE@ toggle
```

---

## 5. Status bar integration

If you use **waybar**, you can show and control audio input/output. Example `~/.config/waybar/config`:

```json
"modules-right": ["pulseaudio"],
```

And in `~/.config/waybar/modules/pulseaudio.json`:

```json
{
  "format-source": "{volume}% ",
  "format-source-muted": "",
  "scroll-step": 5
}
```

This will give you a mic volume/mute indicator.

---

✅ So in short: use `pactl` (or GUI tools like `pavucontrol`) to control input, and add sway/waybar keybinds/modules for easy access.

---

Do you want me to write you a **ready-to-use sway config snippet** with hotkeys for muting and adjusting mic gain?
