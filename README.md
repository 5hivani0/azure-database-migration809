# Azure Database Migration Project #  

## Description ##  


## What i learnt ##  


## Tasks accomplished in each milestone ##  
## Milestone 1: Set up the Environment ##
1. I set up this GitHub Repo to document the development of this project.
2.  I set up an Azure account with login credentials that i will use thoughout this project.  


## Milestone 2: Set up the Production Environment ##
1. Virtual Machine Creation
    - Created a Windows Virtual Machine named production-vm.
    - Assigned the VM to the resource group named my-vm-rg.
2. Network Configuration
    - Configured appropriate network settings to ensure secure communication.
    - Enabled RDP protocol for secure remote connections.
3. Remote Connection
    - Initiated a remote connection to the VM using Microsoft Remote Desktop and the RDP protocol.
4. SQL Server and SSMS Installation
    - Installed SQL Server on the VM to serve as the database server.
    - Installed SQL Server Management Studio (SSMS) for effective database management.
5. AdventureWorks Database Restoration
    - Obtained a backup file of the AdventureWorks database.
    - Restored the AdventureWorks database on the production server.
    - The AdventureWorks database serves as a sample database, emulating a fictional manufacturing company's operations.

## Milestone 3: Migrate to Azure SQL Database ##
1. SQL Databse Setup
    - Created a SQL Database named my-database.
    - Placed the database in the resource group named my-database-rg.
    - Assigned the database to a server named my-server-shivani.
2. Configure SQL Firewall Rules
    - Added a firewall rule for SQL Server with the VM's IP address as the start and end IP addresses.
    - Ensured that the VM can securely connect to the SQL Server.
3. Azure Data Studio installaiton
    - Set up Azure Data Studio on the production Windows VM.
    - Established a connection to the existing on-premise database using Azure Data Studio.
    - Established a connection to the newly created Azure SQL Database.
4. Install SQL Server Schema Compare Extension
    - Installed the SQL Server Schema Compare extension within Azure Data Studio.
    - Utilised this extension to compare and migrate the schema from the on-premise database to the Azure SQL Database.
5. Install Azure SQL Migration Extension
    - Installed the Azure SQL Migration extension within Azure Data Studio.
    - Utilised this extension to facilitate the migration of data from the on-premise database to the Azure SQL Database.
6. Database Migration Validation
    - Confirmed the success of the migration process through a comprehensive validation.
    - Thoroughly inspected the migrated database, including data, schema, and configurations, to ensure a successful migration that adheres to principles of data integrity.

 ## Milestone 4: Data Backup and Restore ##
1. Backup the On-Premise Database
    - w
2. Create Blob Storage
    - w
3. Upload Backup to Blob Storage
    - w
4. Restre Database on Development Environment
    - w
5. Automate Backups for Development Database
    - w

## Milestone 5: Disaster Recovery Simulation ##
1. Mimic Data Loss in Production Environment
    - w
2. Restore Database from Azure SQL Database Backup
    - w

## Milestone 6: Geo Replication and Failover ##
1. Set up Geo-replcation for Azure SQL Database
    - w
2. Test Failover and Failback
    - w

## Milestone 7: Microsoft Entra Directory Integration ##
1. Configure Microsoft Entra ID for Azure
    - w
2. Create DB Reader User
    - w
