
![Logo](https://github.com/udhaya-un/SonarQube/blob/master/GeppettoIcon.png?raw=true"Logo")

# Docker With SonarQube<br/>
   In here we will see how to containerize sonarqube in Docker.
   
# Content
1. [Prerequisites](#prerequisites)
1. [DockerCompose File](https://github.com/KishanRavindran/Angularlearning/blob/master/docs/docker-compose.yml)

# Prerequisites<br/> 
  [Install docker](https://docs.docker.com/install/)
         
# Docker Compose File:<br/>
 
    version: '3.3'
     services:
      db:
       image: postgres
       restart: always
       volumes:
         - $PWD/db:/var/lib/postgresql/data
       environment:
         POSTGRES_PASSWORD: sonar
         POSTGRES_USER: sonar

       sonarqube:
         image: sonarqube
         restart: always
         ports:
           - 9000:9000
           - 9092:9092
       volumes:
         - $PWD/sonar:/opt/sonarqube/data
       depends_on:
          - db
       environment:
         SONARQUBE_JDBC_USERNAME: sonar
         SONARQUBE_JDBC_PASSWORD: sonar
         SONARQUBE_JDBC_URL: jdbc:postgresql://db/sonar
         
         
  open the directory of this file in terminal and run the following commang to up the containers
  **docker-compose up -d**
         
        
