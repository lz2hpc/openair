## ADS-B Reception with RTL_SDR dongle and Docker

Instead of installing the decoder and a vizualization software natively, 

we may do this using docker engine and run them in docker containers.

### Install and configure the Docker

#### Install Docker

Download a script and install the *docker* and the *docker-copmpose*:

```
curl -fsSL https://get.docker.com -o get-docker.sh

sh get-docker.sh

docker-compose --version

```

In case some errors (like version failed) occurs perform next extra steps:

```
sudo pip uninstall docker docker-compose

sudo apt-get update

sudo apt-get upgrade

sudo apt-get install docker docker-compose

```

#### Configure Docker

Add docker log rotation, as the logs and amount of data ```/var/lib/docker/containers``` in will grow.

Edit the daemon config ```/etc/docker/daemon.json```

```

{
"log-driver": "json-file",
"log-opts": {
    "max-size": "10m",    
    "max-file": "3" 
    }
}

```
Restart the docker daeomon ```systemctl restart docker```

### Install RTL-SDR drivers

For ADS-B reception we will use cheap RTL_SDR dongle.

First we need to blacklist the default drivers. To do this, 

create a file ```/etc/modprobe.d/blacklist-rtl2832.conf``` containing the following:

```
blacklist rtl2832
blacklist dvb_usb_rtl28xxu
blacklist rtl2832_sdr

```

Install the drivers: ``` apt-get install rtl-sdr```.

Check if the device is visible and we can use it: ```rtl_test```.

And even with some SDR receiving software like GQRX: 

```
apt-get install pulseaudio

pulseaudio -D

apt-get install gqrx-sdr

gqrx-sdr

```

### Readsb Decoder and tar1090 Images

Create ```/opt/adsb/docker-compose.yml``` and edit it with next configuration data

```
version: '2.0'

networks:
  adsbnet:

services:

  readsb:
    image: mikenye/readsb:latest
    tty: true
    container_name: readsb
    restart: always
    devices:
      - /dev/bus/usb/001/003:/dev/bus/usb/001/003
    ports:
      - 8080:80
      - 30005:30005
    networks:
      - adsbnet
    command:
      - --dcfilter
      - --device-type=rtlsdr
      - --fix
      - --forward-mlat
      - --json-location-accuracy=2
      - --lat=42.61541
      - --lon=23.33497
      - --mlat
      - --modeac
      - --ppm=0
      - --net
      - --stats-every=3600
      - --quiet
      - --write-json=/var/run/readsb

  tar1090:
    image: mikenye/tar1090:latest
    tty: true
    container_name: tar1090
    restart: always
    environment:
      - TZ=Europe/Sofia
      - BEASTHOST=readsb
    networks:
      - adsbnet
    ports:
      - 8078:80
```

Here we have next custom lines:

- /dev/bus/usb/BUSNUMBER/DEVICENUMBER
    
    BUSNUMBER=001
    
    DEVICENUMBER=003

Where 001, 003 are numbers taken from libusb execution. 

- TZ=[Europe/Sofia](https://en.wikipedia.org/wiki/List_of_tz_database_time_zones)

Now we are aible to see the flying planes around us on http://ourhost:8078

### Arrange Feeders

[adsbexchange.com, FlightAware, FlightRadar24, AirNav RadarBox, PlaneFinder](https://github.com/mikenye/docker-readsb/wiki/Guide-to-ADS-B-Data-Receiving,-Decoding-and-Sharing,-Leveraging-RTLSDR-and-Docker)


### Resources

[ADS-B receiving with Docker](https://github.com/mikenye/docker-readsb/wiki/Guide-to-ADS-B-Data-Receiving,-Decoding-and-Sharing,-Leveraging-RTLSDR-and-Docker)

[docker-compose version problem](https://github.com/docker/docker-py/issues/1502)

[Docker log rotation](https://success.docker.com/article/how-to-setup-log-rotation-post-installation)

[Nooelec SDR on Linux](https://www.nooelec.com/store/downloads/dl/file/id/72/product/0/nesdr_installation_manual_for_ubuntu.pdf)

[Time Zone Names](https://en.wikipedia.org/wiki/List_of_tz_database_time_zones)
