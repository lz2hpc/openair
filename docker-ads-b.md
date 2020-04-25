## ADS-B receiving with Docker

### Install and configure the Docker

Download and a script and install the *docker* and the *docker-copmpose*:

```
curl -fsSL https://get.docker.com -o get-docker.sh
sh get-docker.sh
```

```
sudo pip uninstall docker docker-compose

sudo apt-get update

sudo apt-get upgrade

sudo apt-get install docker docker-compose

```

Add docker log rotation, as the logs may grow.

Edit the daemon config ```/etc/docker/daemon.json```

```

{
"log-driver": "json-file",
"log-opts": {
    "max-size": "10m",    
    "max-file": "3" 
    }
}

```
Restart the docker daeomon ```systemctl restart docker```

#### Resources

[ADS-B receiving with Docker](https://github.com/mikenye/docker-readsb/wiki/Guide-to-ADS-B-Data-Receiving,-Decoding-and-Sharing,-Leveraging-RTLSDR-and-Docker)

[docker-compose version problem](https://github.com/docker/docker-py/issues/1502)

[docker log rotation](https://success.docker.com/article/how-to-setup-log-rotation-post-installation)
