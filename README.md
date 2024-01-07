# Azure Database Migration Project #  

## Description ##  
This Azure Database Migration project involved designing and implementing a cloud-based database on Microsoft Azure. This included setting up a production database and seamlessly migrating to Azure SQL Database. Key steps included creating a production and development environment, data backup, restoration procedures, and automated scheduling. Disaster recovery scenarios were simulated with geo-replication and failover configuration for improved data availability, and Microsoft Entra ID integration enhanced security through access role definition.

## What I learnt ##  
Throughout this project, I've successfully designed and implemented a cloud-based database system on Microsoft Azure, showcasing my practical expertise in cloud engineering. The initial steps involved setting up a production environment database, followed by a seamless migration to Azure SQL Database. This migration process was particularly focused on key aspects such as creating a development environment, data backups using blob storage, restoration procedures, and automated scheduling, significantly reinforcing my data management skills.

A crucial phase of the project included simulating a disaster recovery scenario with potential data loss. This allowed me to delve into the intricacies of geo-replication and failover configuration, testing data availability in the event of unforeseen disruptions. This experience not only honed my disaster recovery skills but also provided valuable insights into maintaining data integrity and continuity.

In terms of security measures, I integrated Microsoft Entra ID to define access roles, adding an extra layer of control and safeguarding to the database system. This action strengthened the overall security framework, showcasing my dedication to implementing robust access controls and ensuring the protection of sensitive data.

Overall, this project has equipped me with a comprehensive skill set in architecting and managing cloud-based database systems on Microsoft Azure. From initial setup and migration to disaster recovery simulations and security enhancements, each phase has contributed to my hands-on expertise in cloud engineering.

## The Documented Stages of Development for this Project ##  
## Stage 1: Setting up the Environment ##
1.  Created this GitHub Repository to document the development of this project.
2.  Set up an Azure account with login credentials that will be used throughout this project, ensuring accessibility and authorisation for project-related activities on the Azure platform.  


## Stage 2: Setting up the Production Environment ##
1. Virtual Machine Creation
    - Created a Windows Virtual Machine (VM), within its own resource group, dedicated to being an isolated production environment.
2. Network Configuration
    - Configured appropriate network settings to ensure secure communication.
    - Enabled RDP protocol for secure remote connections.
3. Remote Connection
    - Initiated a remote connection to the VM using Microsoft Remote Desktop and the RDP protocol.
4. SQL Server and SSMS Installation
    - Installed SQL Server on the VM to serve as the database server.
    - Installed SQL Server Management Studio (SSMS) for effective database management.
    - Both essential tools required for effective database management and interaction.
5. AdventureWorks Database Restoration
    - Obtained a backup file of the AdventureWorks database.
    - Restored the AdventureWorks database on the production server.
    - The AdventureWorks database serves as a sample database, emulating a fictional manufacturing company's operations.

## Stage 3: Migrating to Azure SQL Database ##
1. SQL Database Setup
    - Set up an SQL Database within a designated resource group on a specified server, optimizing database organisation and management.
2. Configuring SQL Firewall Rules
    - Added a firewall rule for SQL Server with the VM's IP address as the start and end IP addresses.
    - Ensured that the VM can securely connect to the SQL Server.
3. Azure Data Studio Installation
    - Set up Azure Data Studio on the production Windows VM.
    - Established a connection to the existing on-premise database using Azure Data Studio.
    - Established a connection to the newly created Azure SQL Database.
4. Installing SQL Server Schema Compare Extension
    - Installed the SQL Server Schema Compare extension within Azure Data Studio.
    - Utilised this extension to compare and migrate the schema from the on-premise database to the Azure SQL Database.
5. Installing Azure SQL Migration Extension
    - Installed the Azure SQL Migration extension within Azure Data Studio.
    - Utilised this extension to facilitate the migration of data from the on-premise database to the Azure SQL Database.
6. Database Migration Validation
    - Confirmed the success of the migration process through comprehensive validation.
    - Thoroughly inspected the migrated database, including data, schema, and configurations, to ensure a successful migration that adheres to principles of data integrity.

 ## Stage 4: Data Backup and Restoration ##
1. Backup the On-Premise Database
    - Generated a full backup of the production database on my production VM.
2. Creating Blob Storage
    - Configured a Blob storage account and container to serve as a secure online repository for my database backups.
3. Uploading Backup to Blob Storage
    - Uploaded the previously created backup file to my Blob storage container, to provide an extra layer of backup protection
4. Restoring the Database on the Development Environment
    - Created a development VM for the purpose of testing, developing, and experimenting. This safeguards the production environment, ensuring its uninterrupted functionality and preserving the data integrity of critical production data.
    - Installed SQL Server and SSMS to provide necessary database infrastructure.
    - Downloaded the backup file stored previously in my Blob storage container.
    - Restored the database on my development VM.
5. Automating Backups for the Development Database
    - Created credentials to access my storage account from SSMS.
    - Created a maintenance plan in SSMS that automated regular weekly backups of my development database to my Azure Blob storage, ensuring consistent protection for my evolving work and simplifying recovery of my development environment if needed.

## Stage 5: Disaster Recovery Simulation ##
1. Mimicing Data Loss in the Production Environment
    - To mimic data loss, in Data Studio, I simulated data corruption of the Production table in the database by creating a query that updated the top 100 rows of the ProductionDescription column with the value 'n/a'.
    - After running the simulation, I verified the data corruption was present in the Production table.
    - I ran the data corruption simulation at 10:59:24 AM on 21/12/2023.
2. Restoring the Database from the Azure SQL Database Backup
    - In the Azure portal, I used restore on the SQL Database Backup to create a restored version of the database from the point in time of 09:00:00 AM on 21/12/2023, roughly 2 hours before the corruption was made. This version was saved by the name of production-database-restored.
    - Through the connection on Azure Data Studio, I verified this restored database deployment had been successful.
    - Through the Azure portal, I then deleted the previous database which contained the corruption, to make the restored database that contains all the critical information the new production database.

## Stage 6: Geo-Replication and Failover ##
1. Setting up Geo-replication for the Azure SQL Database
    - I set up geo-replication for my production Azure SQL Database by creating a synchronised replica of my primary database, with the creation of a replication server, with a location set to (US) East US, with SQL authentication.
2. Testing Failover and Failback
    - Carried out a planned failover to the secondary region to evaluate the availability and data consistency of the failover database.
    - This was to provide insight into the failover mechanisms and to assess that there will be continous data availability and minimised downtime in the case of unforeseen disruptions.
    - Verified the failover had been successful and the database had been transferred over with no issues.
    - Performed a tailback to the primary region to demonstrate the cyclical nature of my failover strategy.

## Stage 7: Microsoft Entra Directory Integration ##
1. Configuring Microsoft Entra ID for Azure SQL Database
    - Enabled Microsoft Entra ID authentication for the SQL Server hosting my Azure SQL production database to integrate it as a trusted identity provider.
    - Designated myself as the Microsoft Entra admin with privileged permissions for user management and access control, ensuring the ability to connect to the production database using Microsoft Entra credentials in Azure Data Studio.
2. Creating a Read-Only User
    - Created a new user in Microsoft Entra ID.
    - After connecting to the production database using my Microsoft Entra Admin credentials, I assigned the db_datareader role to the new user I created, so that they are granted read-only privileges.
    - This is important as it is vital that the production environment remains accurate and consistent, and so restriciting access ensures other users, such as fellow team members, can still derive necessary insight without the risk of unintended data modification.
    - Verified the assigned role given to the user by reconnecting to the production database using Azure Data Studio and the new read-only user credentials, to then test that the user can only perform tasks that they have been permitted to do.

  
## UML Diagram Illustrating the Architecture I Have Built ##
![Azure Project Diagram](https://github.com/5hivani0/azure-database-migration809/assets/149093767/b402b2f4-7cd3-4531-8b5e-0b1329bc8c3d)
  
## License ##
MIT

