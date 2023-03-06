# Docker

## Install
###### Arch
`$ sudo pacman -S docker docker-compose`



###### Ubuntu
`$ sudo apt-get install docker docker-compose`

###### Docker and docker compose prerequisites
```
sudo apt-get install curl
sudo apt-get install gnupg
sudo apt-get install ca-certificates
sudo apt-get install lsb-release
```

##

## EXEC command
###### Getting inside the container
`$ docker exec [OPTIONS] CONTAINER COMMAND [ARG..]`

###### Example:
`$ docker exec -it cis-backend-1 bash`

##

## Setup
###### Allow docker to run on startup
```
$ systemctl start docker
$ sudo gpasswd -a $(whoami) docker
$ sudo docker ps
$ sudo systemctl start docker
$ sudo systemctl enable docker
$ sudo systemctl restart docker
```
## 

## Troubleshooting
###### If you get a problem with docker.sock
`$ sudo chmod 666 /var/run/docker.sock`

##

## Manage
###### Buil and Up / Down
```
$ cd path/to/docker-compose/file/
$ docker-compose up -d --build
or
$ docker-compose down
```

###### Remove images and something
`$ docker rm $(docker ps -aq)`
`$ docker rmi $(docker images -q)`

###### Check logs
```
$ cd path/to/docker-compose/file/
$ docker-compose logs -f
or
$ docker-compose logs <container-name?> -f
```

###### Clear cache
`$ docker system prune`

##

## On UBUNTU, dont use apt to install docker compose
###### OLD VERSION
`$ sudo curl -L "https://github.com/docker/compose/releases/download/1.27.4/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose`

`$ sudo chmod +x /usr/local/bin/docker-compose`

```
$ which docker-compose
/usr/local/bin/docker-compose
```

```
$ docker-compose -v
docker-compose version 1.27.4, build 40524192
```

###### NEW VERISON
`$ sudo curl -L "https://github.com/docker/compose/releases/download/2.10.2/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose`
##




Install using the repository
Before you install Docker Engine for the first time on a new host machine, you need to set up the Docker repository. Afterward, you can install and update Docker from the repository.

Set up the repository
Update the apt package index and install packages to allow apt to use a repository over HTTPS:

 sudo apt-get update
 sudo apt-get install \
    ca-certificates \
    curl \
    gnupg \
    lsb-release
Add Docker’s official GPG key:

 sudo mkdir -p /etc/apt/keyrings
 curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /etc/apt/keyrings/docker.gpg
Use the following command to set up the repository:

 echo \
  "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.gpg] https://download.docker.com/linux/ubuntu \
  $(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
Install Docker Engine
Update the apt package index, and install the latest version of Docker Engine, containerd, and Docker Compose, or go to the next step to install a specific version:

 sudo apt-get update
 sudo apt-get install docker-ce docker-ce-cli containerd.io docker-compose-plugin
Receiving a GPG error when running apt-get update?

Your default umask may not be set correctly, causing the public key file for the repo to not be detected. Run the following command and then try to update your repo again: sudo chmod a+r /etc/apt/keyrings/docker.gpg.

To install a specific version of Docker Engine, list the available versions in the repo, then select and install:

a. List the versions available in your repo:

 apt-cache madison docker-ce
b. Install a specific version using the version string from the second column, for example, 5:20.10.16~3-0~ubuntu-jammy.

 sudo apt-get install docker-ce=<VERSION_STRING> docker-ce-cli=<VERSION_STRING> containerd.io docker-compose-plugin
Verify that Docker Engine is installed correctly by running the hello-world image.

 sudo docker run hello-world
