# Installation of jOAI
This document describes how to install joai running within tomcat6 on a Ubuntu machine. 

## Environment
Ubuntu 14.04 server

##Prerequisites
### 1. Update and upgrade if necessary
```sh
apt-get update
apt-get upgrade
```

### 2. Download and unpack jOAI Software
See http://www.dlese.org/dds/services/joai_software.jsp for details.

The current version can be downloaded from Sourceforge, e.g. as zip file

```sh
wget https://sourceforge.net/projects/dlsciences/files/jOAI%20-%20OAI%20Provider_Harvester/v3.1.1.4/joai_v3.1.1.4.zip
unzip joai_v3.1.1.4.zip
```

### 3. Install tomcat
In the INSTALL.txt of teh joi package above it is recommended to download
the Tomcat server container from http://tomcat.apache.org/ .
But in most cases (and in case of Ubuntu version 12 and greater) you can use the pre-installed Tomcat package.  
The current version of tomcat is 7, but joai runs as well within tomcat6.
```sh
sudo apt-get install tomcat7
```

### 3a. Tomcat trouble shooting
One known problem with tomcat is, if you have another web server, e.g. an apache running on the same machine.
... further information about trouble shooting can be found at 
...!!!...
or ask for support at EUDAT help desk ...??? 

### 4. Set localhost name
?? Maybe a good idea for OAI server as well - never tried !!?? 
```sh
hostnamectl set-hostname new-hostname
echo "IPa.ddr.ess new-hostname" >> /etc/hosts
```

### 5. Add the web application jOAI to the Tomcat container
Place the file 'oai.war' into the 'webapps' directory found in    
your Tomcat installation directory. 'webapps' is the default location where Tomcat 
expects to find web applications.
```sh
cp joai_v3.1.1.4/oai.war /var/lib/tomcat7/webapps/
```
During the first start tomcat will unpack the application 'oai'.

## 6. Install Java Platform, Standard Edition v5 or later
Tomcat needs the Java Run Time environment (JRE).
Often this is already preinstalled on ubuntu by apt-get update.

You can check the instalation (path) e.g. by 
```sh
readlink -f $(which java)
``` 

If java isn't installed, install at least JRE :
```sh
sudo apt-get install default-jdk
```

Finally set the environment variable JRE_HOME, e.g. :
JRE_HOME=/usr/lib/jvm/java-7-openjdk-amd64/jre/bin/java


## Start and stop Tomcat
### 7. 

Try to start tomcat
```sh
sudo service tomcat7 start
```

If you now enter in an internet browser
```sh
localhost:8080
```
and all woks fine you should see 

... !!! add a figure with the 'It works' page !!!

and 
```sh
localhost:8080
```

Congratultaions !

Now you can configure and use your OAI-PMH provider and harvester
as described in 
....!!!
