### FlightRadar24

#### Install FlightRadar24 

Install and configure feeder via next script:

``sudo bash -c "$(wget -O - https://repo-feed.flightradar24.com/install_fr24_rpi.sh)"``

    ...
        Preparing to unpack .../fr24feed_1.0.23-8_armhf.deb ...
        Unpacking fr24feed (1.0.23-8) ...
        Setting up fr24feed (1.0.23-8) ...
        You don't seem to have any dump1090 installed. On the fr24feed start it will automatically install dump1090-mutability.
        Created symlink /etc/systemd/system/multi-user.target.wants/fr24feed.service → /etc/systemd/system/fr24feed.service.

#### Statistics

- Pi Host: http://localhost:8754

- My Data Sgharing: https://www.flightradar24.com/account/feed-stats/?id=19030

#### Start / Stop

``$ sudo service fr24feed start``

``$ sudo service fr24feed restart``

``$ sudo service fr24feed restart``

#### Logs

``$ tail -f /var/log/fr24feed/fr24feed.log``

#### Resources

https://thepihut.com/blogs/raspberry-pi-tutorials/how-to-track-aircraft-with-your-raspberry-pi

https://www.flightradar24.com/build-your-own
https://repo-feed.flightradar24.com/rpi_images/fr24-raspberry-pi-latest.img.zip
