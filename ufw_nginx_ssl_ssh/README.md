# NGINX, SSL, and UFW

## UFW

## NGINX
###### On Action:
`$ rm /etc/nginx/sites-enabled/default`
* this is a link: default -> /etc/nginx/sites-available/default

`$ cp ~/cis/nginx/app.conf /etc/nginx/conf.d/`
* assuming that we have a working copy of conf file to the /etc/nginx/conf.d/

```
$ sudo systemctl stop nginx
$ sudo syttemctl start nginx
```

###### Config file

```
server {
	listen 80;

	location / {
		proxy_pass http://localhost:3000;
		proxy_http_version 1.1;
		proxy_set_header Upgrade $http_upgrade;
		proxy_set_header Connection "Upgrade";
  	}
}
```
* Currently working on VBox Ubuntu Server and Docker



## SSL




###### Install and setup 
https://ubuntu.com/tutorials/install-and-configure-nginx#4-setting-up-virtual-host

##



### NGINX
###### Good to read regarding NGINX
https://nickjanetakis.com/blog/why-i-prefer-running-nginx-on-my-docker-host-instead-of-in-a-container

##


### Nginx
####### You can see which apps are available by running this command:
`$ sudo ufw app list`

####### Simple way to add them to UFW:
`$ ufw allow 80,443/tcp`

####### If you are wanting to accomplish this via application you will need to create the application ini file within /etc/ufw/applications.d
`$ vim /etc/ufw/applications.d/nginx.ini`

####### Place this inside file:
```
[Nginx HTTP]
title=Web Server
description=Enable NGINX HTTP traffic
ports=80/tcp

[Nginx HTTPS] \
title=Web Server (HTTPS) \
description=Enable NGINX HTTPS traffic
ports=443/tcp

[Nginx Full]
title=Web Server (HTTP,HTTPS)
description=Enable NGINX HTTP and HTTPS traffic
ports=80,443/tcp
```

####### Then type this commands
```
$ ufw app update nginx
$ ufw app info 'Nginx HTTP'
$ ufw allow 'Nginx HTTP'
```
```
sudo ufw allow 80
sudo ufw allow "Nginx FULL"
sudo ufw status
sudo ufw app list
```

####### 2022 from the resouces
INSTALLATION: https://nginx.org/en/linux_packages.html#Ubuntu

##



### NGNIX
####### Install
```
$ sudo apt install nginx
$ service nginx status

 # after that go check your ip on the browser:

 # 		http://ip.add.re.ss

	
$ sudo apt install nginx
$ sudo nano /etc/nginx/sites-available/default

```

######	Add the following to the location part of the server block
```
    server_name yourdomain.com www.yourdomain.com;

    location / {
        proxy_pass http://localhost:5000; #whatever port your app runs on
        proxy_http_version 1.1;
        proxy_set_header Upgrade $http_upgrade;
        proxy_set_header Connection 'upgrade';
        proxy_set_header Host $host;
        proxy_cache_bypass $http_upgrade;
    }
```

####### Check NGINX config
	
`$ sudo nginx -t`

####### Restart NGINX
		
`$ sudo service nginx restart`

##


### UFW
######	to start
```
$ sudo ufw enable
$ sudo ufw default deny
```

####### to check
```
$ sudo ufw status
$ sudo ufw status verbose
```

####### with number

`$ sudo ufw status numbered`

####### & to delete (use the numbers)

`$ sudo ufw delete <NUM>`

####### & before NGINX
```
$ sudo ufw enable
$ sudo ufw status
$ sudo ufw allow ssh (for Port 22)
$ sudo ufw allow http (for Port 80)
$ sudo ufw allow https (for Port 443)
```

##


### SSL Self signed: LetsEncrypt
######
```
$ sudo add-apt-repository ppa:certbot/certbot
$ sudo apt-get update
$ sudo apt-get install python-certbot-nginx
$ sudo certbot --nginx -d yourdomain.com -d www.yourdomain.com

Only valid for 90 days, test the renewal process with

$ certbot renew --dry-run
```

##

### OpenSSH - Server  
###### Installation and LINK 
`$ sudo apt install openssh-server`

https://www.cyberciti.biz/faq/ubuntu-linux-install-openssh-server/

###### Allow ssh from firewall
`$ sudo ufw allow ssh`

###### Enable
`$ sudo systemctl enable ssh`

###### Start
`$ sudo systemctl start ssh`

###### To see status

###### If you get a Public permision error, modify sshd config file
```
place steps here
```

##