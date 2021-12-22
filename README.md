# DC_Promoteos_Grafana
DockerCompose  Promoteos &amp; Grafana

## Install Docker
### Install Java (CentOS)
	$ sudo mkdir /usr/java
	$ wget
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

### Install Python (CentOS)
	$ sudo yum install -y python36 python36-libs python36-devel python36-pip
	$ sudo yum groupinstall -y "Development Tools"
	$ sudo update-alternatives --install /usr/bin/python python /usr/bin/python2.7 1
	$ sudo update-alternatives --install /usr/bin/python python /usr/bin/python3.6 2
	$ sudo alternatives --config python
## Install Docker
### Download Packages :
	docker-ce-19.03.9-3.el7.x86_64.rpm
	docker-ce-cli-19.03.9-3.el7.x86_64.rpm
	containerd.io-1.2.6-3.3.el7.x86_64.rpm
### Install
	$ sudo yum install docker-ce-19.03.9-3.el7.x86_64.rpm docker-ce-cli-19.03.9-3.el7.x86_64.rpm containerd.io-1.2.6-3.3.el7.x86_64.rpm -y
	$ sudo systemctl enable docker
	$ sudo systemctl start docker
	
For Checking :

	$ sudo docker run hello-world




## Install compose at Fedora

	$ sudo dnf update -y
	$ sudo curl -L "https://github.com/docker/compose/releases/download/1.29.2/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose
	$ sudo dnf install docker-compose -y
	$ sudo chmod +x /usr/local/bin/docker-compose

test docker-compose if fails :

	 $ sudo ln -s /usr/local/bin/docker-compose /usr/bin/docker-compose

