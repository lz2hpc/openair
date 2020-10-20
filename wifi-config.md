### Wifi Configuration

Default credentials: pi / raspberry

``sudo nano /etc/wpa_supplicant/wpa_supplicant.conf``

```
network={
  ssid="HUAWEI-B311-C47C"
  psk="46AM41FL214"
  key_mgmt=WPA-PSK
}
```

#### Resources

[https://www.raspberrypi.org/documentation/configuration/wireless/wireless-cli.md](https://www.raspberrypi.org/documentation/configuration/wireless/wireless-cli.md)

https://dev.to/vorillaz/headless-raspberry-pi-zero-w-setup-3llj
