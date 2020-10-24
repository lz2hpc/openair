#### Instructions

1. Read: https://pimylifeup.com/raspberry-pi-remote-desktop/

2. On the ubuntu computer: install remina

3. On the raspberry pi:

Code: Select all

```
sudo apt-get update
sudo apt-get upgrade
sudo apt-get install xrdp
hostname -I
```

... write down the IP address from the "hostname -I" command

4. reboot your RP machine

5. On the Ubunu 18.04 machine: set up a new profile:
- give it a name like "RDP to Pi"
- choose RDP protocol in the protocol pull down menu
- in the server box, type in the IP you got from issuing "hostname -l" on your raspberry pi
- enter the username of your rasperry pi machine (usually this is "pi" if you haven't changed it)
- enter the password of your raspberry pi machine (this can be blank if you have not explicitly changed your password on your RP machine).
- click on "Save"
- click on "Connect"


#### Resources

[https://www.raspberrypi.org/forums/viewtopic.php?t=250393](https://www.raspberrypi.org/forums/viewtopic.php?t=250393)
