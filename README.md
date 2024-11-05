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
![image](https://github.com/user-attachments/assets/68ea66b0-adf8-43ed-9e02-554e2bdf5907)

2) Create a Virtual Network with Subnets for Web, App, and DB
![image](https://github.com/user-attachments/assets/4ee757b5-c229-4f24-832a-570781ea62bf)
![image](https://github.com/user-attachments/assets/417a0815-298f-491f-a9b9-309e70f372c5)


Step 3: Create Network Security Groups (NSGs)
Defined rules to allow or deny traffic between subnets and external networks.
1) Create NSGs for Web, App, and Database Tiers
![image](https://github.com/user-attachments/assets/51cdf1da-384e-4067-9d34-773ebeff2ce2)
![image](https://github.com/user-attachments/assets/35cdd6c0-3ae2-41d9-bb4f-55e3b387e4b0)

2) Add NSG rules for Web tier (allow HTTP, HTTPS, and SSH):
![image](https://github.com/user-attachments/assets/90941594-8226-468e-a7cf-145b867654e2)

3) Associate NSGs with subnets
![image](https://github.com/user-attachments/assets/a6c2d0b3-5e14-41c6-8e32-9464b2f8f016)

![image](https://github.com/user-attachments/assets/a5e0081a-b15c-4d67-887b-2a199f8c6e8b)







