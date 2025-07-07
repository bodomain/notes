
## 🔧 Step-by-Step: Assign a Static IPv4


- **List the network interfaces**:

   ```bash
   nmcli device
   ```

   Identify the primary interface, e.g., `eth0` or `ens18`.

- **Assign a static IPv4**:
   Replace `ens18`, `192.168.1.100`, `24`, and `192.168.1.1` with desired IP, CIDR, and gateway.

   ```bash
   nmcli con modify ens18 ipv4.addresses 192.168.1.100/24
   nmcli con modify ens18 ipv4.gateway 192.168.1.1
   nmcli con modify ens18 ipv4.method manual
   nmcli con modify ens18 ipv4.dns "8.8.8.8 1.1.1.1"
   nmcli con up ens18
   ```

- **Verify**:

   ```bash
   ip addr
   ping -c 3 8.8.8.8
   ```

---
