# Docker Compose 

Three parts 

Services 

Networks 

Ports 

# Basic Commands 

sudo service docker start 

sudo service docker status 

sudo service docker stop 

# Dockerfile for tomcat war deployment 

File content 

FROM openjdk:11-jdk-slim 

MAINTAINER knkhattar 

COPY target/wartest.war /usr/local/tomcat/webapps/ 

# Build Image 

sudo docker image build -t knkhattar/mytomcatcontainer . 

# Run It 

sudo docker container run -it --publish 8081:8080 knkhattar/mytomcatcontainer 

Check it on browser http://localhost:8080/ 

# Docker Container 

Docker container ls 

Docker container stop mysql 

Docker rm  

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
