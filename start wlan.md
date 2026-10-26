Activating WLAN in Arch Linux from the command line involves two main steps: bringing the network interface up, and then connecting to a network. The exact method depends on which network management tool you have installed.

### 🔌 Step 1: Bring the Interface Up

First, identify your wireless interface name (it usually starts with `wlan` or `wl`):

```bash
ip link
```

Once you have the name (e.g., `wlan0`), bring it up. You also need to ensure it is not blocked by hardware or software switches.

```bash
# Bring the interface up
sudo ip link set wlan0 up

# Check if it is blocked (look for "soft blocked: yes")
rfkill list

# If it is soft-blocked, unblock it
sudo rfkill unblock wlan
```
If you encounter an error mentioning `RF-kill`, the `rfkill` commands above are the solution .

### 📡 Step 2: Connect to a Network

Arch Linux does not have a default network manager, so you must use the tool you installed. Here are the most common command-line options:

**If you use `iwd` (recommended for minimal setups):**
The `iwctl` tool is an interactive command-line interface.

1.  Launch it: `iwctl`
2.  Scan and connect (replace `wlan0` with your interface name):
    ```text
    station wlan0 scan
    station wlan0 get-networks
    station wlan0 connect "Your_SSID"
    ```
    You will be prompted for the password .

**If you use `netctl` (traditional Arch tool):**
You can use the interactive `wifi-menu` (requires the `dialog` package):

```bash
sudo wifi-menu
```
Alternatively, you can copy an example profile from `/etc/netctl/examples/` to `/etc/netctl/`, edit it with your SSID and password, and then run `sudo netctl start your_profile` .

**If you use `NetworkManager`:**
Use the `nmcli` command-line tool:

```bash
# List available networks
nmcli device wifi list

# Connect to a network
nmcli device wifi connect "Your_SSID" password "Your_Password"
```

**If you use `ConnMan`:**
First, enable the wifi technology, then connect:

```bash
# Enable wifi
sudo connmanctl enable wifi

# Scan and connect (you may need to enter the interactive prompt for the agent)
sudo connmanctl scan wifi
sudo connmanctl services
sudo connmanctl connect wifi_<unique_id>
```
*Note: ConnMan often requires running `agent on` in its interactive prompt to successfully connect to protected networks* .

### 💡 Troubleshooting Tip

If the interface refuses to come up or scan, ensure your wireless chipset firmware is installed. You can check for firmware loading errors with:
```bash
dmesg | grep -i firmware
```
If you see missing firmware errors, you will need to install the appropriate firmware package (e.g., `linux-firmware`) for your card .