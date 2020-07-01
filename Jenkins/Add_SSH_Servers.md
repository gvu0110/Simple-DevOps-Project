# Add SSH Server in Publish over SSH
1. In Jenkins, move the private key `id_rsa` to the folder `/var/lib/jenkins/.ssh` and update permission
```
sudo chown jenkins:jenkins /var/lib/jenkins/.ssh/id_rsa
sudo chmod 0400 /var/lib/jenkins/.ssh/id_rsa
```
- Path to key: `/var/lib/jenkins/.ssh/id_rsa`
- Name: `tomcat-docker`
- Hostname: `35.183.51.101`
- Username: `dockeradmin`

2. In Docker host, allow `dockeradmin` SSH into
```
sudo su dockeradmin
mkdir /home/dockeradmin/.ssh
sudo cp /home/ec2-user/.ssh/authorized_keys /home/dockeradmin/.ssh/authorized_keys
chmod 700 .ssh
chmod 600 .ssh/authorized_keys
```
