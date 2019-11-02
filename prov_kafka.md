#### Install

``$ sudo useradd kafka -m``

``$ sudo passwd kafka``

``$ sudo adduser kafka sudo``

``$ su -l kafka``

``$ mkdir ~/Downloads``

``$ curl "https://www.apache.org/dist/kafka/2.3.1/kafka_2.12-2.3.1.tgz" -o ~/Downloads/kafka.tgz``

``$ mkdir ~/kafka && cd ~/kafka``

``$ tar -xvzf ~/Downloads/kafka.tgz --strip 1``

#### Configure

``$ nano ~/kafka/config/server.properties``

add ``delete.topic.enable = true``

``$ sudo nano /etc/systemd/system/zookeeper.service``

with content:

```

[Unit]
Requires=network.target remote-fs.target
After=network.target remote-fs.target

[Service]
Type=simple
User=kafka
ExecStart=/home/kafka/kafka/bin/zookeeper-server-start.sh /home/kafka/kafka/config/zookeeper.properties
ExecStop=/home/kafka/kafka/bin/zookeeper-server-stop.sh
Restart=on-abnormal

[Install]
WantedBy=multi-user.target

```

``$ sudo nano /etc/systemd/system/kafka.service``

```

[Unit]
Requires=zookeeper.service
After=zookeeper.service

[Service]
Type=simple
User=kafka
ExecStart=/bin/sh -c '/home/kafka/kafka/bin/kafka-server-start.sh /home/kafka/kafka/config/server.properties > /home/kafka/kafka/kafka.log 2>&1'
ExecStop=/home/kafka/kafka/bin/kafka-server-stop.sh
Restart=on-abnormal

[Install]
WantedBy=multi-user.target

```

#### Status / Start / Stop / Restart

``$ sudo systemctl status kafka``

``$ sudo systemctl start kafka``

``$ sudo systemctl stop kafka``

``$ sudo systemctl restart kafka``

Journalctl Info:

``$ sudo journalctl -u kafka``

``$ sudo journalctl -xe``

#### GUI

https://github.com/tchiotludo/kafkahq

https://www.conduktor.io/download $$$

#### Resources

https://www.digitalocean.com/community/tutorials/how-to-install-apache-kafka-on-ubuntu-18-04
