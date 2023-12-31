# Project: Run Nexus on Droplet and Publish Artifact to Nexus

## Technologies used:
- Nexus
- DigitalOcean
- Linux
- Java
- Gradle

## Project Requirements:
- Install and configure Nexus from scratch on a cloud server
- Create new User on Nexus with relevant permissions
- Java Gradle Project: Build Jar & Upload to Nexus

****

### in Droplet
```sh
apt update
apt install openjdk-8-jdk
wget https://download.sonatype.com/nexus/3/nexus-3.61.0-02-unix.tar.gz

tar -zxvf nexus-3.61.0-02-unix.tar.gz

adduser nexus

chown -R nexus:nexus nexus-3.61.0-02
chown -R nexus:nexus sonatype-work/

vim nexus-3.61.0-02/bin/nexus.rc

su - nexus
$ /opt/nexus-3.61.0-02/bin/nexus start

netstat -plnt | grep 8081

cat /opt/sonatype-work/nexus3/admin.password
4b083135-b282-47f9-8bff-51af288758c9
```
******
### in Nexus
- create a user
- create a role
- assign the role to the user

****

### build and publish the project

```cmd
gradle build
gradle publish
```

******


