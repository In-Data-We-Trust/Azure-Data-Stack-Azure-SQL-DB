# How to use Github and Azure together

## References

* https://github.com/marketplace/actions/azure-sql-deploy

## Investigations on how to create an Azure SQL DB 

* **Source** - https://github.com/marketplace/actions/azure-sql-deploy#-end-to-end-examples
  * Following the end-to-end example so it can be captured

### Making the Azure SQL DB

The standing up of the original Azure SQL DB Instance can be done in a variety of ways shown here (https://learn.microsoft.com/en-gb/azure/azure-sql/database/single-database-create-quickstart?tabs=azure-powershell&view=azuresql#create-a-single-database):

* Portal or
* Azure CLI or 
* Azure CLI (Sql Up) or
* Powershell

To keep it simple, I will opt to do it all in **powershell**

They have pre-defined templates we can use, which save a **lot** of time! 🚀

