
--Scale grid will expire--

 <!--SECTION AWS Cloud  -->

 Connecting to a cloud with SSH - can only use command line

 -Cloud machines are linux based enviroments-

  create an aws account https://aws.amazon.com/ will likely require an active credit card. - Set up mulitfactor auth * says Jake

  SERVICES -Search for-  EC2 - Virtual machines --Maybe star it so it stays

  Lots of stuff on the dashboards - dont worry

  Select California

  -Can host your own VPN with this... There is openvpn.net-

  Instances - launch an instance
      Select free stuff, shouldn't be charged

  Change Quick Start to Ubuntu  (yum install is aws apt is not)

  Architecture (x86) - Not enough support for (Arm)

  Instance type --  Stay on free tier *Can spend a lot of money very fast on the cloud*

  Connection Create new key pair -- Create key pair Name it something, a very unique key pair only one download

  Network settings -- cHECK OFF https AND http additionally for what we are doing.

  create a securtiy group -- you get one vpc for free, 
  name - openToInternet

  Inbound Security Group Rules 
      Type ssh, anywhere

  Add custom
      MYSQL/Aurora --auto port 3306-- 
      Source Type Anywhere --Typically very dangerous, no sensitive data - so it'll work for demo

  --Launch-- 

  Connect - SSH Client
  example: has an example command prompt

  Register as known machine

  sudo - super user do
  Python is pre installed


Test connection in VS Code
  Create AWS_CLASSROOM
  HOST: Ip_address of the ec2 box
  Username - created user Password created password
  Connect and save

  <!--SECTION NODE -->

  sudo curl -sL https://deb.nodesource.com/setup_18  --enter-->

  repeat command -o ~/node_setup.sh

  sudo apt-get instal-y ca-certificates crul gnupg

  NODE_MAJOR=18

  PM2 and nodemon
<!-- FIXME unfinished demonstration -->

<!-- SECTION Git flow NGINX -->
ctrl+R and shift+R to pull up previous commands helps pull old commands
enter through pem key

If it needs a server, you cannot use github pages.

NGINX is a proxy
update and upgrade

sudo apt install nginx
sudo nginx - fails to bind
sudo systemctl status nginx make sure it says enabled --ctrl+c-- got out of status
navigate to nginx folder cd into it
cd into sites-available
cd into default
sudo nano default
server{
    listen 80;l
    listen [::]:80
    server_name "EC2 IP-address";

    location / {
        copy and paste from readme -big proxy thing- probaly not white space sensitive so probably wont break it
        port: 3000
    }
    location /-otherProject-{
        port: 3001
    }
}

sudo systemctl restart nginx
sudo systemctl stats nginx
ctrl+c

in bcw file app.use('/gregslist',express-_-_-) - it was previously '' which would provide the wrong url.

setup.js
const routePrefix = process.env.ROUTE_PREFIX || ''
----routePrefix + _-_-
.env
ROUTE_PREFIX = /gregslist

<!--SECTION GitHub Actions -->
respository  .github create workflows folder create deploy.yml file
.yml is white space sensitive with out the right spaces itll break.


security actions secrets new secret

Name* EC2_USERNAME
SECRET*  
ubuntu

NAME*  EC2_IP_ADDRESS

EC2_PEM_KEY
copy/paste from beginning to end no space or extra enters

PnPm a package manager that is faster
in terminal
npm i -g pnpm
pnpm install

<!-- SECTION Thursday stuff -->

SSL lets encrypt -- open source way to get ssl certificates
certbot can give you a guided walk through on cert
---nginx---ubuntu---
default

connect to server
install snapd -- click --  click on ubuntu --- 
sudo apt update
sudo snap
sudo apt install snapd
sudo snap install --classic certbot
sudo ln -s /snap/bin/certvot /user/bin/certbot

<!-- Make sure youve done this first -->

in default -- server_nmae needs a domain. 
<!--  -->
sudo cerbot --nginx
enter email address - needs valid
y, n
Trying our Ip address, will probably fail.
will not cert bare Ip's

free domain registration
free nom -- was down but will provide super long ugly names for free.
squarespace domains sells domains

enter domain name

<!--  -->
bought domain through google domains
uses CLOUDFLARE for DNS services -- offers domain names, cheaper prices then square space domain

in CF add record Name @ is for the root and can add the ip address -- dont proxy for demo, a proxy is another layer of protection

You want Full(strict) <SSL/TLS> Overview
-can maybe skip cerbot if you bother to set up CF

<!-- SECTION Full Strict set up / instead of certbot -->
-Should be free-
Origin Server - create certificate
RSA(2048)
Cert Validity 15years
will give a wildcard cert  *.domain.win
gives orgin cert and private key -- need to be added to ec2 box

inside nginx sites-available default

server {
    listen 80;
    listen [::]:80;
    server_name yourdomain.com;   # Replace with your domain or public IP
    *server_name yourdomain.com;
    return 301 https://$server_name$request_uri;
}

server {
    listen 443 ssl http2;
    listen [::]:443 ssl http2;
    server_name yourdomain.com;

    <!-- Need to add these files where they are being called from -->
    sudo nano /etc/ssl/cert.pem
    sudo nano /etc/ssl/key.pem
    sudo nginx -t //check for okay
    sudo systemctl restart
    sudo systemctl restart nginx

    ssl_certificate /etc/ssl/cert.pem;
    ssl_certificate_key /etc/ssl/key.pem;

    location / {
        proxy_pass http://127.0.0.1:3000;
        proxy_http_version 1.1;
        proxy_set_header Upgrade $http_upgrade;
        proxy_set_header Connection "upgrade";
        proxy_set_header Host $host;
        proxy_set_header X-Real-IP $remote_addr;
        proxy_set_header X-Forwarded-For $proxy_add_x_forwarded_for;
        proxy_set_header X-Forwarded-Proto $scheme;
        proxy_read_timeout 86400;
    }
}


recommends kylecodes.dev something like that

<!-- SECTION Docker -->
Docker 
Kubernetes
DockerHub

sudo snap install docker
    at ~$

sudo docker ps
sudo docker pull codeworkscontainers/saintmarys