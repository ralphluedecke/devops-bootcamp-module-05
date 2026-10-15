# Cloud and Infrastructure as a Service - IaaS
## setup digital ocean
### create digital ocean account
- go to "https://www.digitalocean.com"
- do signup process
### configure ssh keys
```bash
ssh-keygen -t rsa
```
put public key in ~/USER/.ssh./id_rsa.pub under ssh keys in digital ocean
### create droplet
- click "create droplet" in digital ocean
- choose 4GB version, ubuntu linux
### open ssh ports
- open droplet
- click networking
- create firewall
- add port 22 as an inbound rule
- add port 7071  as an inbound rule
### ssh into server
on your local computer do

```bash
ssh root@(IP of droplet)
```
### install java
first do update
```bash
apt-get update
```

install java
```bash
apt install openjdk-25-jre-headless
```
check version
```bash
java -version
```
install gradle
```bash
apt install gradle
```
check version
```bash
gradle -v
```
## build, deploy and run java app on remote server
### build
- clone repo https://gitlab.com/twn-devops-bootcamp/latest/05-cloud/java-react-example
- change into project dir 
```bash
gradle build
```

### deploy
take the created jar and copy it to the server
```bash
scp *.jar root@(IP of droplet)
```

### run
logon to the server and execute the jar
```bash
java -jar *.jar
```

# general security hints
1. create a new admin user
2. assign only needed roles
3. assign correct directory rights

# resources from nana
- https://gitlab.com/twn-devops-bootcamp/latest/05-cloud/java-react-example