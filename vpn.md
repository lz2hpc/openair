### Open VPN Settings

#### Server

``$ wget https://git.io/vpn -O openvpn-install.sh``

``$ sudo bash openvpn-install.sh``

#### Client

``$ sudo apt-get install openvpn -y``

``$ openvpn –-version``

From the Public server get the ``client.ovpn`` file and 

put it on the clien's location ``/etc/openvpn/client.ovpn``.

Initialize the client with the config file.

``$ openvpn ./client.ovpn``

#### Start / Stop

``$ sudo systemctl stop openvpn@server``

``$ sudo systemctl start openvpn@server``

``$ sudo systemctl restart openvpn@server``

#### Boot

``mv /etc/openvpn/client.ovpn /etc/openvpn/client.conf``

Add ``AUTOSTART="all"`` to ``/etc/default/openvpn``



#### Resources

[https://www.cyberciti.biz/faq/howto-setup-openvpn-server-on-ubuntu-linux-14-04-or-16-04-lts/](https://www.cyberciti.biz/faq/howto-setup-openvpn-server-on-ubuntu-linux-14-04-or-16-04-lts/)


