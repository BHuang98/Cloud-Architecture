# Cloud-Architecture
Utilizing Azure to create a Cloud Architecture environment simulating real world application
**Step 1: Define the Cloud Architecture**
For this project I'm going to create a 3-tier architecture:
Tier 1 (Frontend): Webservers running on VM behind load balancer
Tier 2 (Application): Application server running on separate VM
Tier 3 (Database): A managed Azure SQL Database

Step 2: Set Up the Virtual Network (VNet)
Created a Virtual Network to allow secure communication between the web, application, and database tiers.
1) Created resource group
2) ![image](https://github.com/user-attachments/assets/68ea66b0-adf8-43ed-9e02-554e2bdf5907)
