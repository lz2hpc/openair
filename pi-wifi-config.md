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

If the WiFi is not working, continue with:

``sudo nano /etc/network/interfaces``

```
auto lo
iface lo inet loopback

iface eth0 inet manual

auto wlan0
allow-hotplug wlan0
iface wlan0 inet manual
        wpa-conf /etc/wpa_supplicant/wpa_supplicant.conf
```
And enable: ``sudo systemctl enable wpa_supplicant.service``

After a restart Wifi will be Up and running.

#### Resources

[https://www.raspberrypi.org/documentation/configuration/wireless/wireless-cli.md](https://www.raspberrypi.org/documentation/configuration/wireless/wireless-cli.md)


[https://dev.to/vorillaz/headless-raspberry-pi-zero-w-setup-3llj](https://dev.to/vorillaz/headless-raspberry-pi-zero-w-setup-3llj)

[https://linuxhint.com/rasperberry_pi_wifi_wpa_supplicant/](https://linuxhint.com/rasperberry_pi_wifi_wpa_supplicant/)

[https://community.octoprint.org/t/solved-raspberry-pi-2b-wifi-issues-with-buster-and-octopi/16960](https://community.octoprint.org/t/solved-raspberry-pi-2b-wifi-issues-with-buster-and-octopi/16960)
