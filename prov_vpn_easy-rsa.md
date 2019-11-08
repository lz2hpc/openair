#### Install

``wget -P ~/ https://github.com/OpenVPN/easy-rsa/releases/download/v3.0.6/EasyRSA-unix-v3.0.6.tgz``


``

Common Name (eg: your user, host, or server name) [Easy-RSA CA]:penguin_vpn_01

CA creation complete and you may now import and sign cert requests.
Your new CA certificate file for publishing is at:
/etc/openvpn/easy-rsa/EasyRSA-v3.0.6/pki/ca.crt


root@221303:/etc/openvpn/easy-rsa/EasyRSA-v3.0.6# ./easyrsa gen-req penguin_vpn_01

Note: using Easy-RSA configuration from: ./vars

Using SSL: openssl OpenSSL 1.1.1b  26 Feb 2019
Generating a RSA private key
...............................................
-----
Common Name (eg: your user, host, or server name) [penguin_vpn_01]:

Keypair and certificate request completed. Your files are:
req: /etc/openvpn/easy-rsa/EasyRSA-v3.0.6/pki/reqs/penguin_vpn_01.req
key: /etc/openvpn/easy-rsa/EasyRSA-v3.0.6/pki/private/penguin_vpn_01.key


``


#### Resources

[Easy-RSA Releases](https://github.com/OpenVPN/easy-rsa/releases)

[How To Set Up an OpenVPN Server on Debian 9](https://www.digitalocean.com/community/tutorials/how-to-set-up-an-openvpn-server-on-debian-9)
