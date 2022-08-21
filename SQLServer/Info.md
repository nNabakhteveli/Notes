## Docker image for Microsoft SQL Server on mac
Since you can not directly use Microsoft SQL Server on macos, you need to pull its docker image from dockerhub:

```docker pull mcr.microsoft.com/mssql/server:2019-latest```

But you cant really use ```mcr.microsoft.com/mssql/server:2019-latest``` containers on mac M1 because MSSQL DB does not support ARM architecture. The only way I found is to use Azure SQL container that supports ARM and can be run on M1.

Use docker-compose.yml config file (see docker-compose.yml file)

or

```docker pull mcr.microsoft.com/azure-sql-edge:latest```


You will be able to connect to this DB using: 

      username: sa, 
      password: Passw@rd
      database: master 
   
If you want other db name - you can create a new one using SQL: CREATE DATABASE TestDB

This database has the same API as MSSQL DB, so it works with pyodbc (not supported on M1) and pymssql libraries.

If you are using it on M1 machine, consider using pymssql library for connection to Azure SQL DB


Login to MSSQL from commandline: `mssql -u <USERNAME> -p <PASSWORD>`
