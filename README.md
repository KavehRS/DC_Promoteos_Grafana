# DC_Promoteos_Grafana
DockerCompose  Promoteos &amp; Grafana

## Install Docker & Dependencies
### Install Java (CentOS 7)
	$ sudo mkdir /usr/java
	$ wget https://github.com/KavehRS/website/blob/master/FileServer/oracle.com/otn-pub/java/jdk/8u221-b11/jdk-8u221-linux-x64.tar.gz
	$ sudo tar -zxvf jdk-8u221-linux-x64.tar.gz -C /usr/java
	$ sudo vi /etc/profile.d/java.sh

 
Add to /etc/profile.d/java.sh 

	export JAVA_HOME=/usr/java/jdk1.8.0_221
	export PATH=$PATH:$JAVA_HOME/bin
	export CLASSPATH=.:$JAVA_HOME/jre/lib:$JAVA_HOME/lib:$JAVA_HOME/lib/tools.jar
<br>

	$ source /etc/profile.d/java.sh
	$ sudo update-alternatives --install /usr/bin/java java /usr/java/jdk1.8.0_221/bin/java 1
	$ sudo update-alternatives --install /usr/bin/javac javac /usr/java/jdk1.8.0_221/bin/javac 1
	$ sudo update-alternatives --config java
	$ java -version

### Install Python (CentOS 7)
	$ sudo yum install -y python36 python36-libs python36-devel python36-pip
	$ sudo yum groupinstall -y "Development Tools"
	$ sudo update-alternatives --install /usr/bin/python python /usr/bin/python2.7 1
	$ sudo update-alternatives --install /usr/bin/python python /usr/bin/python3.6 2
	$ sudo alternatives --config python
	
	
	
### Set Dns in Centos 7 (for shecan.ir)

Edit network config

	# vi /etc/sysconfig/network-scripts/ifcfg-eth0
	
<br>
	
Edit or Add DNSs (for example):

	DNS1="1.1.1.1"
	DNS2="1.0.0.1"

	
<br>


	$ sudo systemctl restart NetworkManager



### Install Docker
Download Packages :

	$ wget  https://github.com/KavehRS/website/blob/master/FileServer/linux/centos/7/x86_64/stable/Packages/docker-ce-19.03.9-3.el7.x86_64.rpm
	$ wget https://github.com/KavehRS/website/blob/master/FileServer/linux/centos/7/x86_64/stable/Packages/docker-ce-cli-19.03.9-3.el7.x86_64.rpm
	$ wget https://github.com/KavehRS/website/blob/master/FileServer/linux/centos/7/x86_64/stable/Packages/containerd.io-1.2.6-3.3.el7.x86_64.rpm
	
Install

	$ sudo yum install docker-ce-19.03.9-3.el7.x86_64.rpm docker-ce-cli-19.03.9-3.el7.x86_64.rpm containerd.io-1.2.6-3.3.el7.x86_64.rpm -y
	$ sudo systemctl enable docker
	$ sudo systemctl start docker
	
For Checking :

	$ sudo docker run hello-world




## Install Docker-compose at Fedora
### Install at CentOS 7
	$ sudo yum update -y
	$ sudo curl -L "https://github.com/docker/compose/releases/download/2.2.3/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose
	$ sudo chmod +x /usr/local/bin/docker-compose

test docker-compose if fails :

	 $ sudo ln -s /usr/local/bin/docker-compose /usr/bin/docker-compose



### Install at Fedora

	$ sudo dnf update -y
	$ sudo curl -L "https://github.com/docker/compose/releases/download/1.29.2/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose
	$ sudo dnf install docker-compose -y
	$ sudo chmod +x /usr/local/bin/docker-compose

test docker-compose if fails :

	 $ sudo ln -s /usr/local/bin/docker-compose /usr/bin/docker-compose
	 
### Docker Compose For Prometheus + Grafana	 
	 
Clone the repo:: https://github.com/KavehRS/docker-images.git

Then go to prometheus-grafana folder and run docker-compose up -d.

This will start Prometheus on http://localhost:9090 and Grafana on http://localhost:3000.

