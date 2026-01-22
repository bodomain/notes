# Proxmox does not connect to the internet:

Since your gateway (`10.42.0.1`) is a **standard Arch Linux installation**, the issue is almost certainly that Arch isn't currently acting as a router. By default, Linux distros do not forward traffic from one interface to another for security reasons.

To fix this, you need to enable **IP Forwarding** and **IP Masquerading (NAT)** on the Arch machine.

---

### Step 1: Enable IP Forwarding on Arch

This tells the Arch kernel to allow packets from PVE to pass through its networking stack to the internet.

1. **Check if it's already on:**
```bash
sysctl net.ipv4.ip_forward

```


If it says `0`, it is disabled.
2. **Enable it immediately:**
```bash
sysctl -w net.ipv4.ip_forward=1

```


3. **Make it permanent:** Create a file at `/etc/sysctl.d/30-ipforward.conf` and add:
```ini
net.ipv4.ip_forward=1

```



---

### Step 2: Configure NAT (Masquerading) on Arch

Even with forwarding on, your ISP/Main Router doesn't know about the `10.42.0.0/24` network. The Arch machine must "hide" PVE's traffic behind its own IP address.

Assuming your Arch machine connects to the internet via an interface named `eth0` (change this to your actual internet-facing interface, like `wlan0` or `enp3s0`):

1. **Apply the NAT rule:**
```bash
iptables -t nat -A POSTROUTING -o eth0 -j MASQUERADE
iptables -A FORWARD -m conntrack --ctstate RELATED,ESTABLISHED -j ACCEPT
iptables -A FORWARD -i <LAN_INTERFACE> -o eth0 -j ACCEPT

```


*(Note: Replace `<LAN_INTERFACE>` with the interface on Arch that is physically connected to Proxmox).*
2. **Make it permanent:** Arch does not save iptables by default. Use:
```bash
iptables-save > /etc/iptables/iptables.rules
systemctl enable --now iptables

```



---

### Step 3: Test on Proxmox

Once the Arch machine is routing, go back to PVE and try:

```bash
ping 8.8.8.8

```

**If you can ping 8.8.8.8 but NOT `google.com**`, you just need to set the DNS on Proxmox:

1. Edit `/etc/resolv.conf` on PVE.
2. Add: `nameserver 1.1.1.1` or `nameserver 8.8.8.8`.

---

### Summary of the Flow

| Machine | Role | Requirement |
| --- | --- | --- |
| **PVE** | Client | Gateway set to `10.42.0.1`, DNS set to `8.8.8.8` |
| **Arch** | Gateway | `ip_forward=1` and `iptables MASQUERADE` |

**Do you know the name of the internet-facing interface on your Arch machine?** (Run `ip route | grep default` on Arch to find out).