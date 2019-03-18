### RadarBox

Install and configure feeder via next script:

``sudo bash -c "$(wget -O - http://apt.rb24.com/inst_rbfeeder.sh)"``

If there is no dump1090:

``$ sudo rbfeeder --set-network-mode off --no-start``

#### Status

``$ ps -fae | grep rbfeeder``

#### Claim yourself

Get the key:

``$ sudo rbfeeder --showkey --no-start``

Insert the key: https://www.radarbox24.com/raspberry-pi/claim

#### Memory

``$ htop``

#### Statistics

[https://www.radarbox24.com/stations/raspberry-pi](https://www.radarbox24.com/stations/raspberry-pi)
[https://www.radarbox24.com/stations](https://www.radarbox24.com/stations)

#### Start / Stop

``$ sudo systemctl start rbfeeder``

``$ sudo systemctl stop rbfeeder``

``$ sudo systemctl restart rbfeeder``

#### Logs

``$ tail -f /var/log/rbfeeder.log``

#### Links

[sudo rbfeeder --set-network-mode off --no-start](sudo rbfeeder --set-network-mode off --no-start)
