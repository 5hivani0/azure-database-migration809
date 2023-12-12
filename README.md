# Azure Database Migration Project #  

## Description ##  


## What i learnt ##  


## Tasks accomplished in each milestone ##  
## Milestone 1 ##
1. I set up this GitHub Repo to document the development of this project.
2.  I set up an Azure account with login credentials that i will use thoughout this project.  


## Milestone 2 ##
### Virtual Machine setup ###
1. Virtual Machine Creation
    - Created a Windows Virtual Machine named production-vm.
    - Assigned the VM to the resource group named my-vm-rg.
2. Network Configuration
    - Configured appropriate network settings to ensure secure communication.
    - Enabled RDP protocol for secure remote connections.
3. Remote Connection
    - Initiated a remote connection to the VM using Microsoft Remote Desktop and the RDP protocol.

###  SQL Server and SQL Server Management Studio (SSMS) set up ###
1. SQL Server and SSMS Installation
    - Installed SQL Server on the VM to serve as the database server.
    - Installed SQL Server Management Studio (SSMS) for effective database management.
2. Firewall Rule for SQL Server
    - Added a firewall rule for SQL Server with the VM's IP address as the start and end IP addresses.
    - Ensured that the VM can securely connect to the SQL Server.

### Production database set up ###
1. SQL Databse Setup
    - Created a SQL Database named my-database.
    - Placed the database in the resource group named my-database-rg.
    - Assigned the database to a server named my-server-shivani.
2. AdventureWorks Database Restoration
    - Obtained a backup file of the AdventureWorks database.
    - Restored the AdventureWorks database on the production server.
    - The AdventureWorks database serves as a sample database, emulating a fictional manufacturing company's operations.

