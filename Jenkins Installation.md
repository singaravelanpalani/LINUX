
## Ubuntu-18.04 Install Jenkins
- Reference-1: https://www.jenkins.io/doc/book/installing/linux/
- Add the repository & Install the jenkins
```
apt -y update
add-apt-repository ppa:webupd8team/java
apt -y install openjdk-8-jdk
wget -q -O - https://pkg.jenkins.io/debian-stable/jenkins.io.key | sudo apt-key add -
apt-add-repository "deb https://pkg.jenkins.io/debian-stable binary/"
apt-add-repository "deb http://pkg.jenkins-ci.org/debian binary/"
apt -y install jenkins
echo "jenkins ALL=(ALL:ALL) NOPASSWD:ALL" >> /etc/sudoers
systemctl start jenkins; systemctl enable jenkins; systemctl status jenkins
netstate -ntpl | grep 8080
cat /var/lib/jenkins/secrets/initialAdminPassword
```
- Verify the jenkins application access via browser
http://<Server Ip address>:8080/
  
- Port Redirection 80 to 8080 using Firewalld
```
apt install firewalld -y
systemctl start firewalld; systemctl enable firewalld; systemctl status firewalld
firewall-cmd --zone=public --add-masquerade --permanent
firewall-cmd --zone=public --add-forward-port=port=80:proto=tcp:toport=8080 --permanent
firewall-cmd --reload
```

## Ubuntu-20.00 Install Jenkins
- Reference-1: https://www.jenkins.io/doc/book/installing/linux/
- Add the repository & Install the jenkins
```
sudo apt update -y
sudo apt install openjdk-11-jdk -y
java -version
sudo add-apt-repository universe
wget -q -O - https://pkg.jenkins.io/debian-stable/jenkins.io.key | sudo apt-key add -
sudo sh -c 'echo deb https://pkg.jenkins.io/debian-stable binary/ > /etc/apt/sources.list.d/jenkins.list'
sudo apt update -y
apt -y install jenkins
echo "jenkins ALL=(ALL:ALL) NOPASSWD:ALL" >> /etc/sudoers
systemctl start jenkins; systemctl enable jenkins; systemctl status jenkins
netstate -ntpl | grep 8080
cat /var/lib/jenkins/secrets/initialAdminPassword
```
- Verify the jenkins application access via browser
http://<Server Ip address>:8080/
  




