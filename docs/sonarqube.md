
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

  To create the docker container for the postgres run the following command
  **docker run --name postgres -e POSTGRES_USER=sonar -e POSTGRES_PASSWORD=sonar -it postgres**
  To see the created container run the following command,this command shows all the containers
  **docker ps -a**
![postgres](https://github.com/udhaya-un/SonarQube/blob/master/docs/postgres.png?raw=true"postgres")
  
# SonarQube Installation<br/>

To create the docker container for the postgres run the following command
  **docker run --name sonarqube --link postgres -e sonar.jdbc.url=jdbc:postgresql://postgres:5432/sonar -p 9000:9000 -it sonarqube**
  To see the created container run the following command,this command shows all the containers
  **docker ps -a**
![sonar](https://github.com/udhaya-un/SonarQube/blob/master/docs/sonar_container.png?raw=true"sonar")

# How to up the docker-compose file<br/>         
         
  open the directory of this file in terminal and run the following command to up the containers
  **docker-compose up -d**
  
  To run the SonarQube enter the following url in browser
         
     http://localhost:9000
     
![sonarqube](https://github.com/udhaya-un/SonarQube/blob/master/docs/sonarqube.png?raw=true"sonarqube")
     
         
        
