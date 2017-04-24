# ONL Build

## ONIE Images
```
https://github.com/DeltaProducts/
```
## ONL Images
```
```

## Build ONL 

### Ubuntu 16.04

```
sudo apt-get update
sudo apt-get install binfmt-support -y 
sudo apt-get install build-essential -y 
sudo apt-get install apt-transport-https ca-certificates -y
sudo apt-key adv \
               --keyserver hkp://ha.pool.sks-keyservers.net:80 \
               --recv-keys 58118E89F3A912897C070ADBF76221572C52609D
echo "deb https://apt.dockerproject.org/repo ubuntu-xenial main" | sudo tee /etc/apt/sources.list.d/docker.list
sudo apt-get update
sudo apt-get install docker-engine -y 
sudo apt-get install linux-image-extra-$(uname -r) linux-image-extra-virtual -y
sudo apt-get python -y
sudo apt-get install linux-image-generic-lts-trusty
sudo groupadd docker
sudo gpasswd -a ${USER} docker
sudo service docker restart
docker ps
```

### Build

Build Everything
```
// Dockers
cd OpenNetworkLinux
export VERSION=8
make docker
```

Build x86 Targets
```
docker/tools/onlbuilder -8             
apt-cacher-ng
source setup.env 
make amd64
```
