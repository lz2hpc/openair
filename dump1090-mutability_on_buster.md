#### Install

``sudo apt-get update``

``sudo apt-get install lighttpd``

``sudo apt-get install dump1090-mutability``

``sudo lighty-enable-mod dump1090``

or

``sudo bash -c "$(wget -O - https://raw.githubusercontent.com/abcd567a/dump1090/master/install_dump1090_mut_1.15.sh)"``

#### Check

[http://localhost:80/dump1090/gmap.html](http://localhost:80/dump1090/gmap.html)

##### Error

AJAX call failed (error: Not Found). Maybe dump1090 is no longer running? The displayed map data will be out of date.

``sudo wget -O  /etc/udev/rules.d/rtl-sdr.rules "https://raw.githubusercontent.com/osmocom/rtl-sdr/master/rtl-sdr.rules"``

``sudo reboot``

#### Resources

[https://forum.flightradar24.com/threads/10232-How-to-Install-dump1090-mutability_1-15-dev-on-RPi](https://forum.flightradar24.com/threads/10232-How-to-Install-dump1090-mutability_1-15-dev-on-RPi)
