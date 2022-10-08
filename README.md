# Azure-Data-Stack
Contains all the information required to build and deploy an Azure SQL DB as part of our recommended Azure data Stack

*The build is in process, the readme will be updated with the repos that show the rest of the data stack*

## The Target outcome of this repository

* It can be used to create an Azure SQL Database
* It can be used to deploy github action pipelines to make sure all schema changes are deployed with a PR and as code
  * This avoids any quick schema changes and can enable the company wide data model to be controlled
* It contains all the documentation required to use and implement to different organisations

## What Azure Components will it use?

* Azure SQL Database

## Key information to know

When merging to main, all SQL scripts will be taken from [here](https://github.com/In-Data-We-Trust/Azure-Data-Stack-Azure-SQL-DB/tree/main/database_ddls) and a SQL Project will be generated, then published.

The process needs only one ***create table*** for each table, even when adding columns. The pipeline's will review the changes and alter the target schema as needed. 

The only item it will not carry out will 
