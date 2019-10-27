### dump1090-mutability

Prepare the environment:

``$ sudo apt-get update``

``$ sudo apt-get install -y git``

``$ sudo apt-get install -y build-essential``

``$ sudo apt-get install -y debhelper``

``$ sudo apt-get install -y rtl-sdr``

``$ sudo apt-get install -y librtlsdr-dev``

``$ sudo apt-get install -y libusb-1.0-0-dev``

``$ sudo apt-get install -y pkg-config``

``$ sudo apt-get install -y fakeroot``

``$ sudo apt-get install -y curl``

``$ sudo apt-get install -y cron``

``$ sudo apt-get install -y lighttpd``

Get dump1090-mutability:

``$ cd ~/``

``$ sudo mkdir dump1090-mutability``

``$ cd dump1090-mutability``

``$ sudo git clone https://github.com/mutability/dump1090.git`` or get from 
http://http.us.debian.org/debian/pool/main/d/dump1090-mutability/dump1090-mutability_1.15~20180310.4a16df3+dfsg-6_armhf.deb

Build it:

``$ cd ~/dump1090-mutability/dump1090``

``$ sudo dpkg-buildpackage -b``

Install dump1090-mutability:

``$ cd ~/dump1090-mutability``

``$ sudo dpkg -i dump1090-mutability_1.15~dev_*.deb``

``$ cd ~/dump1090-mutability``

``$ sudo dpkg -i dump1090-mutability_1.15~dev_*.deb``

Configure:

``$ sudo lighty-enable-mod dump1090``

``$ sudo /etc/init.d/lighttpd force-reload``

``$ sudo dpkg-reconfigure dump1090-mutability``

#### Data Json

``$ /run/dump1090-mutability/``

#### Check

http://localhost:80/dump1090/gmap.html

#### Problems

    Lighttpd doesn't start
    
    ``sudo apt-get install gamin``

    Problem fetching data from dump1090.
    AJAX call failed (error: Not Found). Maybe dump1090 is no longer running?
    The displayed map data will be out of date.
    
    ``sudo wget -O  /etc/udev/rules.d/rtl-sdr.rules "https://raw.githubusercontent.com/osmocom/rtl-sdr/master/rtl-sdr.rules" --no-check-certificate``

    sudo reboot


#### Resources

[https://forum.planefinder.net/threads/how-to-install-dump1090-mutability_1-15-dev-on-rpi.889/](https://forum.planefinder.net/threads/how-to-install-dump1090-mutability_1-15-dev-on-rpi.889/)

[https://forum.flightradar24.com/threads/10232-How-to-Install-dump1090-mutability_1-15-dev-on-RPi](https://forum.flightradar24.com/threads/10232-How-to-Install-dump1090-mutability_1-15-dev-on-RPi)
