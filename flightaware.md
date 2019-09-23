### FlightAware

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

``$ sudo netstat -tulpn | grep LISTEN``

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
        
#### Start / Stop

``$ sudo systemctl start dump1090-fa``

``$ sudo systemctl stop dump1090-fa``

``$ sudo systemctl restart dump1090-fa``
        
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

- My Pi Host: http://localhost:8080

- My FlightAware ADS-B: https://flightaware.com/adsb/stats/user/UserSurname

#### Start / Stop

``$ sudo systemctl start piaware`` (runing as service by default)

``$ sudo systemctl stop piaware``

``$ sudo systemctl restart piaware``

#### Logs

``$ tail -f /var/log/piaware.log``

#### Resourses
https://flightaware.com/adsb/piaware/build
http://piaware.flightcdn.com/piaware-sd-card-3.7.2.img.zip
