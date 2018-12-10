
![Logo](https://github.com/udhaya-un/SonarQube/blob/master/docs/GeppettoIcon.png?raw=true"Logo")

# Docker With SonarQube<br/>
   In here we will see how to containerize sonarqube in Docker.
   
# Content
1. [Prerequisites](#prerequisites)<br/>
1. [DockerCompose File](https://github.com/KishanRavindran/Angularlearning/blob/master/docs/docker-compose.yml)

# Prerequisites<br/> 
  [Install docker](https://docs.docker.com/install/)
  [Install docker compose](https://docs.docker.com/compose/install/)
         
# Docker Compose File:<br/>

Create the docker compose file as follow,
 
    version: "3"
      services:
      sonarqube:
        image: sonarqube:6.7.1
        restart: always
        environment:
          - SONARQUBE_JDBC_USERNAME=sonar
          - SONARQUBE_JDBC_PASSWORD=v07IGCFCF83Z95NX
          - SONARQUBE_JDBC_URL=jdbc:postgresql://db:5432/sonarqube
        ports:
          - "9000:9000"
          - "9092:9092"
        volumes:
          - sonarqube_conf:/opt/sonarqube/conf
          - sonarqube_data:/opt/sonarqube/data
          - sonarqube_extensions:/opt/sonarqube/extensions
          - sonarqube_bundled-plugins:/opt/sonarqube/lib/bundled-plugins
        depends_on:
          - db

      db:
        image: postgres:10.1
        restart: always
        environment:
         - POSTGRES_USER=sonar
         - POSTGRES_PASSWORD=v07IGCFCF83Z95NX
         - POSTGRES_DB=sonarqube
        volumes:
          - sonarqube_db:/var/lib/postgresql
          - postgresql_data:/var/lib/postgresql/data
      volumes:
        postgresql_data:
        sonarqube_bundled-plugins:
        sonarqube_conf:
        sonarqube_data:
        sonarqube_db:
        sonarqube_extensions:


         
         
  open the directory of this file in terminal and run the following command to up the containers
  **docker-compose up -d**
  
  To run the SonarQube enter the following url in browser
         
     http://localhost:9000
     
![sonarqube](https://github.com/udhaya-un/SonarQube/blob/master/docs/sonarqube.png?raw=true"sonarqube")
     
         
        
