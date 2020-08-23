
# Reference 
https://docs.docker.com/engine/reference/commandline/docker/


# Basic Commands 

sudo service docker start 

sudo service docker status 

sudo service docker stop 

# Command Groups

docker container --help

docker images --help


# docker image

docker image build -t [image tag name e.g name:latest] .   //. is for current directory holding docker file

docker image ls -a // for all images

docker image pull

docker image push

docker image rm

docker image prune //Remove all dangling images. If -a is specified, will also remove all images not referenced by any container.

# docker container

docker container ls //lists running containers

docker container ls -a //lists all containers

docker container run -d [docker_image] // detached mode

docker container run -it [docker_image] /bin/bash   // interactively

docker container run -p 8080:80 [docker_image] // with port mapping

docker container run --rm [docker_image] // remove container(not image) after run

docker container rm [container id or initial 4 chars of it] //removes container

docker container stop [container id or 4 chars]

docker container start [container id of the stopped container]

# logs
sudo docker logs -f <CONTAINER ID>
sudo docker logs <CONTAINER ID>


# Dockerfile for tomcat war deployment 

  File content 

  FROM openjdk:11-jdk-slim 

  MAINTAINER knkhattar 

  COPY target/wartest.war /usr/local/tomcat/webapps/ 

   ## Build Image 

   sudo docker image build -t knkhattar/mytomcatcontainer . 

   ## Run It 

   sudo docker container run -it --publish 8081:8080 knkhattar/mytomcatcontainer 

   Check it on browser http://localhost:8080/ 

# Docker Container 

Docker container ls 

Docker container stop mysql 

Docker rm  

# Docker Compose 

Three parts 

Services 

Networks 

Ports 

# MySQL run 

docker run -p 3306:3306 -d --name mysql -e MYSQL_ROOT_PASSWORD=password mysql/mysql-server 

Docker ps // to check 

docker exec -it mysql bash 

bash-4.2# mysql -uroot –p   //this will ask for root password
                            //from workbench root user might not work - some setting required in mysql

CREATE USER 'user1'@'%' IDENTIFIED BY 'password1'; 

GRANT ALL PRIVILEGES ON * . * TO 'user1'@'%'; 

Quit 

CREATE DATABASE HSEARCH; 

SHOW DATABASES; 


# MSSQL Docker Installation
  #### PULL/RUN
  * docker pull mcr.microsoft.com/mssql/server:2017-latest
  * docker run -e 'ACCEPT_EULA=Y' -e 'SA_PASSWORD=yourStrongPassword2020' -p 1433:1433 -d mcr.microsoft.com/mssql/server:2017-latest
  * once created next time only start the container - docker container start containerId/name
  #### Interactive
  * docker exec -it <container_id|container_name> /opt/mssql-tools/bin/sqlcmd -S localhost -U sa -P yourStrongPassword2020
  * or from mssm tool - servername --> localhost,1433  serverType: DB Engine, Authentication: SQL Server Authentication
  #### SQLCMD 
  * create database test_db;
  * go - enter
  * USE test_db
  * GO
  * CREATE TABLE employee  (  employee_id int,  first_name varchar(255),  last_name varchar(255)  );  
  * INSERT INTO employee (employee_id ,  first_name , last_name)  VALUES (1, 'first_name1', 'last_name1');  
  * INSERT INTO employee (employee_id ,  first_name , last_name)  VALUES (2, 'first_name2', 'last_name2');  
  * ---
  * select name from sys.databases; // LISTS ALL THE DATABASES
  * SELECT * FROM  test_db.INFORMATION_SCHEMA.TABLES; //LISTS test_db tables
  
  #### DATA VOLUMES
  
  docker run -e "ACCEPT_EULA=Y" -e "MSSQL_SA_PASSWORD=yourStrongPassword2020" -p 1433:1433 -v <host directory>/data:/var/opt/mssql/data -v <host directory>/log:/var/opt/mssql/log -v <host directory>/secrets:/var/opt/mssql/secrets -d mcr.microsoft.com/mssql/server:2017-latest
  
# Docker Compose
docker-compose -v //prints version installed
