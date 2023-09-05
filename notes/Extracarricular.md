
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
