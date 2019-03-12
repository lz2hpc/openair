#### Flight Tracking Software

#### dump1090

``$ sudo apt-get install libusb-1.0-0-dev librtlsdr-dev rtl-sdr``

Get and build dump1090 (Dump 1090 is a Mode S decoder specifically designed for RTLSDR devices.)

``$ git clone https://github.com/DesignSparkrs/dump1090``

``$ cd dump1090``

``$ make``

``Following which edit the file /etc/rc.local and before “exit 0” add the line:``

Run dump1090

``$ cd ~pi/dump1090; ./dump1090 --net --net-http-port 80 --interactive &``

Go to pi_host:80 and enjoy the planes around :)

#### FlightAware

Download and install PiAware:

``$ wget http://flightaware.com/adsb/piaware/files/packages/pool/piaware/p/piaware-support/piaware-repository_3.6.3_all.deb``

``$ sudo dpkg -i piaware-repository_3.6.3_all.deb``

``$ sudo apt-get install dump1090-fa`` (/etc/systemd/system/default.target.wants/dump1090-fa.service → /lib/systemd/system/dump1090-fa.service)


#### Status

Find the dump1090:

``$ ps aux | grep dump1090``

Check PiAware local website: ``pi_host:8080``

Check used ports:

``$ sudo apt install net-tools``

``$ sudo netstat -ltnp``

Where: 
    l: display only listening sockets
    t: display tcp connection
    n: display addresses in a numerical form
    p: display process ID/ Program name
    
One can use specific commands:

``$ piaware-status``

        PiAware master process (piaware) is running with pid 442.
        PiAware ADS-B client (faup1090) is running with pid 610.
        PiAware mlat client (fa-mlat-client) is not running.
        Local ADS-B receiver (dump1090-fa) is running with pid 380.

        dump1090-fa (pid 380) is listening for connections on port 30005.
        faup1090 is connected to the ADS-B receiver.
        piaware is connected to FlightAware.

        dump1090 is producing data on localhost:30005.

        Your feeder ID is zzzzz-zzzzz-zzzzz-zzzzz (from /var/cache/piaware/feeder_id)
        
#### Claim yourself

Go to: https://flightaware.com/adsb/piaware/claim

Result:

        Success!
        You claimed the following 1 receivers:

            zzzzz-zzzzz-zzzzz-zzzzz-zzzzz

        Linked PiAware Receivers (you)

        Great news! Your account is associated with the following PiAware receivers and you can view your statistics here:

            Site 98233 - zzzzz-zzzzz-zzzzz-zzzzz-zzzzz: PiAware (Debian Package Add-on) 3.6 claimed just now! ...

#### Memory

``$ htop``

120M of 927M (with Standard Raspbian Desktop GUI, SSH and dump1090-fa)
   
#### Statistics

- pi_host:8080
- My ADS-B https://flightaware.com/adsb/stats/user/UserSurname

#### Start / Stop

``$ sudo systemctl start piaware`` (runing as service by default)

``$ sudo systemctl stop piaware``

``$ sudo systemctl restart piaware``

#### Logs

``$ tail -f /var/log/piaware.log``

#### FlightRadar24

#### Install FlightRadar24 

Install and configure feeder via next script:

``sudo bash -c "$(wget -O - https://repo-feed.flightradar24.com/install_fr24_rpi.sh)"``

    ...
        Preparing to unpack .../fr24feed_1.0.23-8_armhf.deb ...
        Unpacking fr24feed (1.0.23-8) ...
        Setting up fr24feed (1.0.23-8) ...
        You don't seem to have any dump1090 installed. On the fr24feed start it will automatically install dump1090-mutability.
        Created symlink /etc/systemd/system/multi-user.target.wants/fr24feed.service → /etc/systemd/system/fr24feed.service.



#### Start / Stop

``$ sudo service fr24feed start``

``$ sudo service fr24feed restart``

``$ sudo service fr24feed restart``


