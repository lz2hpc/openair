# iot-pi-flights

#### Legend

Imagine that you are flight control tower :)
So here are the steps for this:

#### Hardware

- RTL-SDR receiver [(Receivers comparison)](http://www.radioforeveryone.com/p/group-ads-b-test-19-dongles.html)
- some small PI
- antenna for 1090Mhz
- 50 Ohm coax cable
- several SMA, Type N  connectors, depends on antenna's connector
- optional filter for 1090MHz

#### Schema

--- Antenna --> Filter > PI > PI_HOST | FEED_HOST 

#### OS Image

Get Raspbian image:
http://vx2-downloads.raspberrypi.org/raspbian_full/images/raspbian_full-2018-11-15/2018-11-13-raspbian-stretch-full.zip

Burn to microSD with Etcher

In running Raspbian run the SSH to be able to operate remotely:

``$ sudo raspi-config   /Interfaces/SSH Enable``
