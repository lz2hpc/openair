### dump1090-mutability

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


``$ cd ~/``

``$ sudo mkdir install-dump``

``$ cd install-dump``

``$ sudo git clone https://github.com/mutability/dump1090.git``



``$ cd ~/install-dump/dump1090``

``$ sudo dpkg-buildpackage -b``


``$ cd ~/install-dump``

``$ sudo dpkg -i dump1090-mutability_1.15~dev_*.deb``


``$ cd ~/install-dump``

``$ sudo dpkg -i dump1090-mutability_1.15~dev_*.deb``


``$ sudo lighty-enable-mod dump1090``

``$ sudo /etc/init.d/lighttpd force-reload``


``$ sudo dpkg-reconfigure dump1090-mutability``

#### Data Json

``$ /run/dump1090-mutability/``

#### Check

http://localhost:80/dump1090/gmap.html
