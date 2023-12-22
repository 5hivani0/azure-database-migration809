# Azure Database Migration Project #  

## Description ##  


## What i learnt ##  


## Tasks accomplished in each milestone ##  
## Milestone 1: Set up the Environment ##
1.  Set up this GitHub Repo to document the development of this project.
2.  Set up an Azure account with login credentials that will be use thoughout this project.  


## Milestone 2: Set up the Production Environment ##
1. Virtual Machine Creation
    - Created a Windows Virtual Machine (VM) named production-vm.
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
    - Generated a full back up of the production database on my production-vm.
2. Create Blob Storage
    - Configured a Blob storage account and container to serve as a secure online repository for my database backups.
3. Upload Backup to Blob Storage
    - Uploaded previously created backup file to my Blob storage container, to provide nan extra layer of backup protection
4. Restore Database on Development Environment
    - Created a development VM called development-vm which can be used for testing, developing, and experimenting.
    - Installed SQL Server and SSMS to provide necessary database infrastructure.
    - Downloaded the backup file stored previously in my Blob storage container.
    - Restored the database on my development-vm.
5. Automate Backups for Development Database
    - Created credentials to access my storagea account from SSMS.
    - Created a maintenance plan in SSMS that automated regular weekly backups of my development database to my Azure Blob storage, ensuring consistent protection for my evolving work and to simplify recovery of my development environment if needed.

## Milestone 5: Disaster Recovery Simulation ##
1. Mimic Data Loss in Production Environment
    - To mimic data loss, in Data Studio, i simuluated data corruption of the Production table in the databse by creating a query that updated the top 100 rows of the ProductionDescription column with the value 'n/a'.
    - After running the simulation, i verified the data corruption was present in the Production table.
    - I ran the data corruption simulation at 10:59:24 AM on the 21/12/2023.

3. Restore Database from Azure SQL Database Backup
    - In the Azure protal, i used restore on the SQL Database Backup to create a restored version of the data base from the point in time of 09:00:00 AM on the 21/12/2023, roughly 2 hours before the corruption was made. This version was saved by the name of production-database-restored.
    - Through the connection on Azure Data Studio, i verified this restored database deployment had been successful.
    - Through the Azure portal, i then deleted the previous database (my-databse) with the corruption, to make the restored database that contains all the critical information the new production database.

## Milestone 6: Geo Replication and Failover ##
1. Set up Geo-replcation for Azure SQL Database
    - Set up geo-replication for my production Azure SqL Database by creating a synchronised replica of my priimary databse, with the server name replication-server and location set to (US) East US, with SQL authentication.
2. Test Failover and Failback
    - Carried out a planned failover to the secondary region to evaluate the availability and data consitency of the failover database.
    - Verifed the failover had been successful and the database had been transfered over with no issues.
    - Performed a tailback to the primary region to demonstrate the cyclical nature of my failover strategy.

## Milestone 7: Microsoft Entra Directory Integration ##
1. Configure Microsoft Entra ID for Azure
    - w
2. Create DB Reader User
    - w
