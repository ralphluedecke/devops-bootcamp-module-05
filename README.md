# Cloud and Infrastructure as a Service - IaaS
## setup digital ocean
### create digital ocean account
### configure ssh keys
```bash
ssh-keygen -t rsa
```
put public key in ~/USER/.ssh./id_rsa.pub under ssh keys in digital ocean
### create droplet
click "create droplet" in digital ocean
choose 4GB version, ubuntu linux
### open ssh port 22
open droplet
click networking
create firewall
add port 22 as an inbound rule
add port 7071  as an inbound rule
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

## build, deploy and run java app on remote server
### build
```bash
gradle build
```

### deploy
```bash
scp *.jar root@(IP of droplet)
```

### run
```bash
java -jar *.jar
```

# security hints
1. create a new admin user
2. assign only needed roles
3. assign correct directory rights

# resources from nana
- https://gitlab.com/twn-devops-bootcamp/latest/05-cloud/java-react-example/-/tree/master?ref_type=heads