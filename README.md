minjava
=======

Minimum Viable Java development environment

Prerquisites
============

A fresh install of ubuntu server 

Steps
=====
```shell
sudo apt-get update
sudo apt-get upgrade
sudo apt-get install openjdk-7-jdk
sudo sh -c 'echo "JAVA_HOME=/usr/lib/jvm/java-7-openjdk-amd64" >> /etc/environment'
source /etc/environment

echo $JAVA_HOME

sudo apt-get install tomcat7 tomcat7-admin tomcat7-common tomcat7-user
sudo /usr/share/tomcat7/bin/shutdown.sh
tomcat7-instance-create tomcat

sed -i '/^JDK_DIRS=.*/c\JDK_DIRS=/usr/lib/jvm/java-7-openjdk-amd64' ~/tomcat/bin/setenv.sh

cd ~/tomcat/webapps
wget http://mirrors.jenkins-ci.org/war/latest/jenkins.war
cd ~
~/tomcat/bin/startup.sh

sudo apt-get install git

sudo apt-get install postgresql postgresql-contrib
```

