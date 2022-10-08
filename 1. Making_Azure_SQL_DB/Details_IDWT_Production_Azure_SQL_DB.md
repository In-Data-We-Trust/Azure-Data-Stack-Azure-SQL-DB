# Details and Making IDWT Production Database

## Step one - Make Database Following Steps

The steps followed are outlined here - https://learn.microsoft.com/en-gb/azure/azure-sql/database/single-database-create-quickstart?tabs=azure-portal&view=azuresql#create-a-single-database

Below is a list of key information that may be needed for future reference

- Subscription: Azure Subscription 1
- Resource Group: IDWT_Production
- Database Name: IDWT_Production_SQL
- Server
- Server Name: idwt-production
- Location: (Europe) UK South
- Admin username: azureuser
- Admin password: Don't be silly, not saved here
- Compute and Storage - Basic, 5 DTU's at $6.11 per month
- Connectivity Method: Leaving as Public Endpoint for now so that it can work across other Azure services. - https://learn.microsoft.com/en-gb/azure/azure-sql/database/network-access-controls-overview?view=azuresql
- Firewall Rules: Set to No for both Azure Services and Adding client IP address. This can be changed on a per cloud feature basis
- Ledger: disabled ledger for auditing purposes
  - The initial deployment with enabled ledger functionality wasn't compatible with github pipelines. This isn't required and is more suitable to use-cases where a blockchain ledger is required. One to explore later
  
## Overview of Details Entered

![](2022-10-05-11-49-58.png)

## Confirmation of Deployment

![](2022-10-05-11-53-19.png)
