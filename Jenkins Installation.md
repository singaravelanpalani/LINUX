
## Ubuntu-18.04 Install Jenkins

```
apt -y update
add-apt-repository ppa:webupd8team/java
apt -y install openjdk-8-jdk
wget -q -O - https://pkg.jenkins.io/debian-stable/jenkins.io.key | sudo apt-key add -
apt-add-repository "deb https://pkg.jenkins.io/debian-stable binary/"
apt-add-repository "deb http://pkg.jenkins-ci.org/debian binary/"
apt -y install jenkins
cat /var/lib/jenkins/secrets/initialAdminPassword
```

- Port Redirection 80 to 8080 
```
apt install firewalld -y
systemctl start firewalld
apt install firewalld
firewall-cmd --zone=public --add-masquerade --permanent
firewall-cmd --zone=public --add-forward-port=port=80:proto=tcp:toport=8080 --permanent
firewall-cmd --reload
```
- Reference-1: https://www.jenkins.io/doc/book/installing/linux/
