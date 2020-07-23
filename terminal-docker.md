# MSSQL Docker Installation
  * docker pull mcr.microsoft.com/mssql/server:2017-latest
  * docker run -e 'ACCEPT_EULA=Y' -e 'SA_PASSWORD=myStrongPasword!123' -p 1433:1433 -d mcr.microsoft.com/mssql/server:2017-latest
  * docker exec -it <container_id|container_name> /opt/mssql-tools/bin/sqlcmd -S localhost -U sa -P myStrongPasword!123
