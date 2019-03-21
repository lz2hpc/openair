### Open VPN Settings

#### Server

``$ wget https://git.io/vpn -O openvpn-install.sh``

``$ sudo bash openvpn-install.sh``

#### Client

``$ sudo apt-get install openvpn -y``

``$ openvpn –version``

From server:

``$ sudo cp client.ovpn /etc/openvpn/client.ovpn``

``$ openvpn –config client.ovpn``

#### Start / Stop

``$ sudo systemctl stop openvpn@server``

``$ sudo systemctl start openvpn@server``

``$ sudo systemctl restart openvpn@server``

#### Routing

#### Resources

[https://www.cyberciti.biz/faq/howto-setup-openvpn-server-on-ubuntu-linux-14-04-or-16-04-lts/](https://www.cyberciti.biz/faq/howto-setup-openvpn-server-on-ubuntu-linux-14-04-or-16-04-lts/)


