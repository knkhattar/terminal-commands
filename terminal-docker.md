
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

docker image build -t [image tag name] .   //. is for current directory holding docker file

docker image ls -a // for all images

docker image pull

docker image push

docker image rm

# docker container

docker container ls //lists running containers

docker container ls -a //lists all containers

docker container run -d [docker_image] // detached mode

docker container run -it [docker_image] /bin/bash   // interactively

docker container run -p 8080:80 [docker_image] // with port mapping

docker container run --rm [docker_image] // remove it after run

docker container stop [container id or 4 chars]

docker container start [container id of the stopped container]




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

bash-4.2# mysql -uroot –ppassword 

CREATE USER 'user1'@'%' IDENTIFIED BY 'password1'; 

GRANT ALL PRIVILEGES ON * . * TO 'user1'@'%'; 

Quit 

Create database HSEARCH; 

Show databases; 


# MSSQL Docker Installation
  * docker pull mcr.microsoft.com/mssql/server:2017-latest
  * docker run -e 'ACCEPT_EULA=Y' -e 'SA_PASSWORD=myStrongPasword!123' -p 1433:1433 -d mcr.microsoft.com/mssql/server:2017-latest
  * docker exec -it <container_id|container_name> /opt/mssql-tools/bin/sqlcmd -S localhost -U sa -P myStrongPasword!123
  * or from mssm tool - servername --> localhost,1433  serverType: DB Engine, Authentication: SQL Server Authentication
  * create database testdb;
  * CREATE TABLE Employee  (  EmployeeID int,  FirstName varchar(255),  LastName varchar(255)  );  
  * INSERT INTO dbo.EMPLOYEE (EmployeeID ,  FirstName , LastName)  VALUES (1, 'testName', 'TestLastName');  
  
# Docker Compose
docker-compose -v //prints version installed
