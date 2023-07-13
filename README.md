# maven-project

Simple Maven Project

Setup Jenkins Server
------------------------------------------------------------------
https://www.jenkins.io/doc/book/installing/linux/#red-hat-centos
------------------------------------------------------------------
# Create an EC2 instance on AWS 
  choose the AWS-Linux-AMI when creating instance
  create and use new pem key 
  this key should be saved and converted to ppk using puttygen
# login to Server
# change hostname of server
  hostnamectl set-hostname Jenkins
# Download Jenkins binaries from repo
sudo wget -O /etc/yum.repos.d/jenkins.repo \
    https://pkg.jenkins.io/redhat-stable/jenkins.repo
sudo rpm --import https://pkg.jenkins.io/redhat-stable/jenkins.io-2023.key
sudo yum upgrade
# Add required java dependencies for the jenkins package
sudo dnf install java-17-amazon-corretto-devel : got correct steps from https://awswithatiq.com/how-to-install-java-on-amazon-linux-2023/
# Install Jenkins and restart system service 
  sudo yum install jenkins
  sudo systemctl daemon-reload
  service jenkins start

# ADD JAVA PATH TO BASH FILE
vi ~/.bash_profile
JAVA_HOME=/usr/lib/jvm/java-17-amazon-corretto.x86_64
PATH=$PATH:$HOME/bin:$JAVA_HOME

# Open Jenkins in browser and follow steps to set administrator credentials
http://server-ip:8080
http://44.201.74.207:8080/
JenkinsAdmin/Admin4real

