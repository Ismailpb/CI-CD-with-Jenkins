# Description

In this project we are going to integrate Ansible with Jenkins. Here we are using a simple flask application using ansible. At first we will build a docker image for the Flask Application in a build server and then deploy the container for the application in a Test environment.

### Pre-Requirements

Here I am using ec2-instances to wokr with the project
- Deployment Server
- Build Server
- Test Server
- Github Account
- DockerHub Account

All the installation( Including ansible,jenkins) were done on the deployment server.

### Tools Used
- Ansible
- Docker
- Git
- Jenkins

### Installation Process

At first we need to install ansible on the deployment server by using the below command

```
wget https://releases.hashicorp.com/packer/1.7.5/packer_1.7.5_linux_amd64.zip
unzip packer_1.7.5_linux_amd64.zip
mv packer /usr/bin/

```
Once the ansible installatio completed, we can now install git and Jenkins on the deployment server. Please note that the entire installation is done on the deployment server

```
amazon-linux-extras install epel -y
yum install java-1.8.0-openjdk-devel -y
wget -O /etc/yum.repos.d/jenkins.repo https://pkg.jenkins.io/redhat-stable/jenkins.repo
rpm --import https://pkg.jenkins.io/redhat-stable/jenkins.io.key
yum -y install jenkins
systemctl start jenkins
systemctl enable jenkins
yum install git -y

```
If the installation completed, we can access the jenkins using the deplyment server ip:8080.
```
13.233.84.215:8080

```
We can cat the file mentioned in the browser to login to the jenkins.
```
# cat /var/lib/jenkins/secrets/initialAdminPassword
*******
[root@xxxx ~]#
```

Once we logged in to the jenkin console, it will ask to customize the jenkins. Here we need to choose "Install Suggested Plugins" and it will take sme time to get completed.




