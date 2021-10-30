sudo apt update
sudo apt upgrade
sudo apt install curl apt-transport-https ca-certificates
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -
echo "deb [arch=$(dpkg --print-architecture)] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable" | sudo tee -a /etc/apt/sources.list.d/docker.list
sudo apt update
sudo apt install docker-ce
docker --version
sudo systemctl start docker (stop, restart, status)
sudo systemctl enable docker

Resources:
https://pimylifeup.com/ubuntu-install-docker/
https://www.digitalocean.com/community/tutorials/how-to-install-and-use-docker-on-ubuntu-18-04
https://www.digitalocean.com/community/tutorials/how-to-install-and-use-docker-compose-on-ubuntu-20-04
