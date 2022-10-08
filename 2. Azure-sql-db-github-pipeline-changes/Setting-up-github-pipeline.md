# Provides an Overview of how to set up github pipeline

## First - We need a user to be made

It is best practice to have a user made that will only be used for the github pipeline. This user will need full permissions on the database to make schema changes, make tables, drop tables, alter tables etc.

For our purposes we will name the user `githubuser` 

## Make a sql-workflow.yml file

This yml file configures the github action and when it needs to run. 

We only want it to run on the main/master branch so people can develop as needed in their own branches. It will compile all SQL queries stored in the repository, compile a SQL-Project file and deploy the changes to the database. It will alter the target database as required. 

Additionally it has been configured to only run when files are changed in the following folder on merging to main - https://github.com/In-Data-We-Trust/Azure-Data-Stack/tree/main/database_ddls

The YML file used for in the repository is found here - https://github.com/In-Data-We-Trust/Azure-Data-Stack/blob/main/.github/workflows/sql-workflow.yml

We are leveraging a Github action called `sql-action` which is here - https://github.com/Azure/sql-action

Critically it's important to read the Usage/summary of the yml so we know how to apply it to our needs - https://github.com/marketplace/actions/azure-sql-deploy#-usage

As we want to be able to deploy multiple SQL scripts, we need to use the part that generates a SQLPROJ file.

![](2022-10-06-15-47-19.png)

If needed for further reading, the definition is here - https://github.com/Azure/sql-action/blob/master/action.yml


### Adding a secret 

The YML file needs a secret to access the Azure SQL DB. This has been created by adding it as a GitHub Action Secret:

![](2022-10-06-14-27-10.png)

The connection string template can be found from the Azure portal. Make sure to then update username and password before adding it as a secret!

```
Server=tcp:idwt-production.database.windows.net,1433;Initial Catalog=<database_name>;Persist Security Info=False;User ID=<user>;Password=<password>;MultipleActiveResultSets=False;Encrypt=True;TrustServerCertificate=False;Connection Timeout=30;
```

### Granting user permission Definition

In order for the pipeline to successfully work, the user configured in the pipeline needs a range of permissions:
- View Definition permission
- Alter permission

The query is stored in the All-Things-SQL Repo for granting the user the required permissions https://github.com/In-Data-We-Trust/IDWT-All-Things-SQL

