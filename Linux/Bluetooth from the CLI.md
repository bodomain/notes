
**Example**
```
bash
bluetoothctl
power on
scan on
```

Wait for device to appear.  Let's say the MAC address is 00:11:22:33:44:55
```
scan off
pair 00:11:22:33:44:55
trust 00:11:22:33:44:55
connect 00:11:22:33:44:55
quit
```



