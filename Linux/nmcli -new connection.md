1. Create connection profile:
```
nmcli connection add type wifi con-name MyHomeWifi ifname wlan0 ssid "MySSID"
```

2. Set the password: 
```
nmcli connection modify MyHomeWifi wifi-sec.key-mgmt wpa-psk
nmcli connection modify MyHomeWifi wifi-sec.psk "mypassword"
```


