### Wifi Configuration

Default credentials: pi / raspberry

``sudo nano /etc/wpa_supplicant/wpa_supplicant.conf``

```
country=US
ctrl_interface=DIR=/var/run/wpa_supplicant GROUP=netdev
update_config=1
network={
  ssid="HUAWEI-B311-C47C"
  scan_ssid=1
  psk="46AM41FL214"
  key_mgmt=WPA-PSK
}
```

#### Resources

[https://www.raspberrypi.org/documentation/configuration/wireless/wireless-cli.md](https://www.raspberrypi.org/documentation/configuration/wireless/wireless-cli.md)

[https://dev.to/vorillaz/headless-raspberry-pi-zero-w-setup-3llj](https://dev.to/vorillaz/headless-raspberry-pi-zero-w-setup-3llj)

[https://linuxhint.com/rasperberry_pi_wifi_wpa_supplicant/](https://linuxhint.com/rasperberry_pi_wifi_wpa_supplicant/)
