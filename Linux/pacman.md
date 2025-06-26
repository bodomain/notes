
---
## -Syu

```
sudo pacman -Syu linux linux-firmware networkmanager
```
Breakdown:
-S = install specific packages
-y = refresh package databases
-u = upgrade all installed packages

This:
Ensures you have the latest kernel and firmware
Installs networkmanager (in case it was removed)
Triggers post-install hooks (like regenerating /boot files or systemd units)

---