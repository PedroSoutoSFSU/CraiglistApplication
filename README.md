# Running Application on EC2 (Use Amazon Linux 2)  
### Install Docker/Git/Docker-Compose on EC2  
`sudo su -`  
`yum update`  
`yum install docker`  
`service docker start`  
`usermod -a -G docker ec2-user`  
`curl -L https://github.com/docker/compose/releases/download/1.22.0/docker-compose-$(uname -s)-$(uname -m) -o /usr/local/bin/docker-compose`  
`chmod +x /usr/local/bin/docker-compose`  
`yum install -y git`  

Login to Docker using:
`docker login`  
 
### Get Application Code from Github  
`git clone https://github.com/sfsu-csc-667-fall-2020/final-project-final_project_jlpsahsb.git`  
`cd final-project-final_project_jlpsahsb/back_end/`  

### Run  
Deploy Application (Ensure you `cd` into back_end folder):  
`sudo npm run pull:all`  
`sudo docker swarm init`  
`sudo docker stack deploy -c ../docker-compose.yml simpleCraig`  

OR ~

`sudo npm run deploy`  

<br>
<br>
<br>
  
# MISC DOCKER COMMANDS
### Leave swarm:  
`docker swarm leave --force`

### Delte all images:  
`docker image prune -a`  

### Delte all volumes:  
`docker volume prune`  

### Kill all containers:  
`docker container kill $(docker ps -q)`  
