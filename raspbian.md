#### Check version

``cat /etc/os-release``

#### Install specific deb

``sudo dpkg -i /path/to/deb/file``

``sudo apt-get install -f``

#### Check ssh

``ps -fae | grep ssh``

``netstat -tulpn | grep 22``

``ssh localhost``

``systemctl is-enabled ssh``

``systemctl status ssh``
