# Cloud-Architecture
Utilizing Azure to create a Cloud Architecture environment simulating real world application
**Step 1: Define the Cloud Architecture**
For this project I'm going to create a 3-tier architecture:
Tier 1 (Frontend): Webservers running on VM behind load balancer
Tier 2 (Application): Application server running on separate VM
Tier 3 (Database): A managed Azure SQL Database
Note: make sure all things getting fired up in the azure portal is the same region

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

Step 4: Create Virtual Machines VM for Web and Application tiers
1) Create Web VM
![image](https://github.com/user-attachments/assets/499bc1f0-79c1-4b90-a497-104c84a373f2)
![image](https://github.com/user-attachments/assets/d572b09f-2795-41ff-aeb6-46fbb74dd2ee)

2) Create App VM
![image](https://github.com/user-attachments/assets/73453873-5bbd-443f-9bc4-e8587d8464cc)


Step 5: Set Up Azure SQL Database (or MySQL)
1) Create an Azure Database for MySQL server:
![image](https://github.com/user-attachments/assets/7c45a484-d61d-469a-849c-65a19f1ee870)

2) Add firewall rule to allow AppVM to communicate to DB



Step 6: Set Up a Load Balancer for Web VMs
1) Create the Load Balancer:
![image](https://github.com/user-attachments/assets/e8a9d738-ec9c-472f-bd4c-e41597b0befc)

2) Create A public IP for the Load balancer
![image](https://github.com/user-attachments/assets/6f82f8a3-16c4-487b-ac7a-16454ef5f6d5)

3) Add Web VMs to the Backend Pool:
![image](https://github.com/user-attachments/assets/1b7c7c0f-07cd-4866-869e-17f03f10ab23)

4) Configure the Load Balancer with a Health Probe:
Health probes are used to check the status of a backend pool instance. If the health probe fails to get a response from a backend instance then no new connections will be sent to that backend instance until the health probe succeeds again.
![image](https://github.com/user-attachments/assets/21546248-543c-4e78-ae59-078500fe7fbe)

5) Create Load Balance rule to distribute traffic
![image](https://github.com/user-attachments/assets/0b4ab6d8-2c4a-4428-9fa0-6361d2aedde7)











