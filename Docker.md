[![CircleCI](https://circleci.com/gh/aws/eks-charts.svg?style=svg)](https://circleci.com/gh/aws/eks-charts)

## Docker Install in Ubuntu 18.04

Update Your System:
```sh
apt-get update -y 
```
Install Prerequisite Packages:
```sh
apt-get -y  install apt-transport-https ca-certificates curl gnupg-agent software-properties-common
```
Add the Docker Repositories With GPG & Fingerprint:
```sh
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -
apt-key fingerprint 0EBFCD88
add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable"
```
Install a Docker:
```sh
apt-get install docker-ce docker-ce-cli containerd.io -y 
```
Start the Docker Servers & Enable Permanent :
```sh
systemctl start docker ; systemctl enable docker ; systemctl status docker
```
