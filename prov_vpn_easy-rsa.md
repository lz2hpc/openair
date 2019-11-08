#### Install

``wget -P ~/ https://github.com/OpenVPN/easy-rsa/releases/download/v3.0.6/EasyRSA-unix-v3.0.6.tgz``

#### Configure the EasyRSA

#### Creating the Server Certificate, Key, and Encryption Files

``$ cd /etc/openvpn/easy-rsa/EasyRSA-v3.0.6``

``$ ./easyrsa init-pki``

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


sudo cp /etc/openvpn/easy-rsa/EasyRSA-v3.0.6/pki/reqs/penguin_vpn_01.req /etc/openvpn


./easyrsa import-req /etc/openvpn/penguin_vpn_01.req server_01 -> /etc/openvpn/easy-rsa/EasyRSA-v3.0.6/pki/reqs/server_01.req


./easyrsa sign-req server server_01

Note: using Easy-RSA configuration from: ./vars

Using SSL: openssl OpenSSL 1.1.1b  26 Feb 2019


You are about to sign the following certificate.
Please check over the details shown below for accuracy. Note that this request
has not been cryptographically verified. Please be sure it came from a trusted
source or that you have verified the request checksum with the sender.

Request subject, to be signed as a server certificate for 1080 days:

subject=
    commonName                = penguin_vpn_01


Type the word 'yes' to continue, or any other input to abort.
  Confirm request details: yes
Using configuration from /etc/openvpn/easy-rsa/EasyRSA-v3.0.6/pki/safessl-easyrsa.cnf
Enter pass phrase for /etc/openvpn/easy-rsa/EasyRSA-v3.0.6/pki/private/ca.key:
Check that the request matches the signature
Signature ok
The Subject's Distinguished Name is as follows
commonName            :ASN.1 12:'penguin_vpn_01'
Certificate is to be certified until Oct 23 09:44:07 2022 GMT (1080 days)

Write out database with 1 new entries
Data Base Updated

Certificate created at: /etc/openvpn/easy-rsa/EasyRSA-v3.0.6/pki/issued/server_01.crt


./easyrsa gen-dh -> /etc/openvpn/easy-rsa/EasyRSA-v3.0.6/pki/dh.pem


sudo openvpn --genkey --secret ta.key


sudo cp /etc/openvpn/easy-rsa/EasyRSA-v3.0.6/ta.key /etc/openvpn/

sudo cp /etc/openvpn/easy-rsa/EasyRSA-v3.0.6/pki/dh.pem /etc/openvpn/


With the last step, ll the certificate and key files needed by your server have been generated.


``

#### Generating a Client Certificate and Key Pair


#### Resources

[Easy-RSA Releases](https://github.com/OpenVPN/easy-rsa/releases)

[How To Set Up an OpenVPN Server on Debian 9](https://www.digitalocean.com/community/tutorials/how-to-set-up-an-openvpn-server-on-debian-9)
