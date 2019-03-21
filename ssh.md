### SSH Tunnel

When the Pi "Radar" is already part of the server with a public static IP,

one may create a SSH tunnel to that computer and to access i.e. a running dump1090 web site.

Steps to crate and run the tunnel:

``$ sudo systemctl status ssh``

if no SSH is available, then install it.

``$ sudo apt install -y openssh-server``

Make it bootable on system start.

``$ sudo systemctl enable ssh``

Then start the ssh service if it's not already started. 

``$ sudo systemctl start ssh``

There are two ways to connect to the remote server.

The first one is using **sshpass**, and the second one is by generating a **SSH key**.

##### Variant 1

``$ sudo apt-get install sshpass``

Run the tunnel.

``sshpass -p some_pass ssh -L 8888:192.168.1.60:8080 root@NNN.NNN.NNN.NNN``

##### Variant 2
