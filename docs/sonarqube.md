
![Logo](https://github.com/udhaya-un/SonarQube/blob/master/docs/GeppettoIcon.png?raw=true"Logo")

# Docker With SonarQube<br/>
   In here we will see how to containerize sonarqube in Docker.
   
# Content
1. [Prerequisites](#prerequisites)
1. [postgres Installation](#Postgres-installation)
1. [SonarQube Installation](#sonarqube-installation)
1. [DockerCompose File](https://github.com/udhaya-un/SonarQube/blob/master/docs/docker-compose.yml)

# Prerequisites<br/> 
  [Install docker](https://docs.docker.com/install/)<br/>
  [Install docker compose](https://docs.docker.com/compose/install/)

# postgres Installation<br/>

To create the docker container for the postgres run the following command. Make sure that the given port in the following command is not used already
       
    docker run --name postgres -e POSTGRES_USER=sonar -e POSTGRES_PASSWORD=sonar -it postgres

To see the created container run the following command,this command shows all the containers
    
    docker ps -a

![postgres](https://github.com/udhaya-un/SonarQube/blob/master/docs/postgres.png?raw=true"postgres")
  
# SonarQube Installation<br/>

To create the docker container for the postgres run the following command. Make sure that the given port in the following command is not used already
   
    docker run --name sonarqube --link postgres -e sonar.jdbc.url=jdbc:postgresql://postgres:5432/sonar -p 9000:9000 -it sonarqube
To see the created container run the following command,this command shows all the containers
   
    docker ps -a

![sonar](https://github.com/udhaya-un/SonarQube/blob/master/docs/sonar_container.png?raw=true"sonar")

To run the SonarQube enter the following url in browser
         
     http://localhost:9000/about
     
![sonarqube](https://github.com/udhaya-un/SonarQube/blob/master/docs/sonarqube.png?raw=true"sonarqube")

Click on the login

![Login](https://github.com/udhaya-un/SonarQube/blob/master/docs/login.png?raw=true"Login")

By default, 
    
    userName: admin and password: admin

![credential](https://github.com/udhaya-un/SonarQube/blob/master/docs/credential.png?raw=true"credential")

After login if we need to change the password click on **Administrator** and then click in **My Account**

![account](https://github.com/udhaya-un/SonarQube/blob/master/docs/admin.png?raw=true"account")

Then select the **security** 

![profile](https://github.com/udhaya-un/SonarQube/blob/master/docs/profile.png?raw=true"profile")

![security](https://github.com/udhaya-un/SonarQube/blob/master/docs/security.png?raw=true"security")

Then change the passwor by give the **old password** and **new password**

![changePassword](https://github.com/udhaya-un/SonarQube/blob/master/docs/changePassword.png?raw=true"changePassword")

Login witht the changed password

![changed](https://github.com/udhaya-un/SonarQube/blob/master/docs/changed.png?raw=true"changed")

# Docker Compose File

This is the another way to containerize the sonarqube with postgres. Download the following file

  https://github.com/udhaya-un/SonarQube/blob/master/docs/docker-compose.yml
  
  Make sure that the port given in the file are not in use.

# How to up the docker-compose file<br/>         
         
open the directory of this file in terminal and run the following command to up the containers
   
    docker-compose up -d
  
To run the SonarQube enter the following url in browser
         
     http://localhost:9000/about
     
![sonarqube](https://github.com/udhaya-un/SonarQube/blob/master/docs/sonarqube.png?raw=true"sonarqube")
     
         
        
