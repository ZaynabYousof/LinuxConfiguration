# LinuxConfiguration
Last Project of Nanodegree Program 


- This project it linux server configuration last project of my nanodegree .I made this readme 
  for describe configuration for server and deploying my project 
  
# ssh port for project
 - 2200
# You can view project on 

- URL : http://ec2-13-59-1-189.us-east-2.compute.amazonaws.com/ 
- IP :http://35.158.93.110/ 

# Make user grader 
- add grader  ->  sudo adduser grader
- open sudoers file and search  by -> sudo nano /etc/sudoers.d/grader
- give it sudo                     -> grader ALL=(ALL:ALL) ALL

# update packages 
- update -> sudo apt-get update
- upgrade -> sudo apt-get upgrade

# configure firwall 
- ssh port  -> sudo ufw allow ssh
- port 2200 -> sudo ufw allow 2200/tcp
- port 80   -> sudo ufw allow www
- port 123 -> sudo ufw allow ntp 
- enble ufw -> sudo ufw enable


# change the port to 22  
- go to ->  sudo nano /etc/ssh/sshd_config
- search for  port (Port 22) to (Port 2200)
- Login again -> ssh grader@35.158.93.110 -p 2200

#  login with key (key based )
- create file on my local machine I put it in this repository 
- name tes.pem 
- connect the content with server 
- login with key -> ssh -i tes.pem  grader@35.158.93.110 -p 2200

# block remote login 
- configuration with -> sudo nano /etc/ssh/sshd_config
- Fsearch for  (PermitRootLogin  yes) to (PermitRootLogin  no )
- save changes  -> service ssh restart

#  only key based authentication
- go config  ->  sudo nano /etc/ssh/sshd_config
- search for  that ( PasswordAuthentication yes)  to (PasswordAuthentication no) 
- save -> sudo service ssh restart


# Installing some applications 
- Apache 
- pstegresql
- Git 
- pip 
- flask  
- virtual environment

# Install ,  configure apache and Postegresql  

- Apche -> sudo apt-get install apache2
- mod_wsgi -> sudo apt-get install libapache2-mod-wsgi python-dev
- postgresql -> sudo apt-get install postgresql postgresql-contrib
- creating user and database 

# git project from github 
- go to www -> cd /var/www
- make directory for project ->  sudo mkdir catalog
- clone my project from github and make some configuration 

# finish 
- after some problems and get help from stackoveflow 
