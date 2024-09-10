# Task 1 – Integrate and Run medusa locally
Name- Pawan Bharat Mhaske
Date – 10-08-2024

Step-1
We need some pre-requisites to install Medusa in the local system. i.e. windows
1.	NodeJs
2.	Git
3.	PostgreSQL

a.	NodeJs : https://nodejs.org/en/#home-downloadhead
b.	Git:  https://git-scm.com/download/win
c.	PostgreSQL:  https://www.postgresql.org/download/windows/


![image](https://github.com/user-attachments/assets/702d486a-c05d-493a-8773-f0970e7077af)


# step-2
![image](https://github.com/user-attachments/assets/3d6a3e61-f5f2-4e8c-841e-a138308b6a9f)
Verifying the NodeJs 


![image](https://github.com/user-attachments/assets/459d692e-73bd-460b-89db-282c7bfb0af3)
Verifying the Git


![image](https://github.com/user-attachments/assets/38c5e90d-c0f8-4f41-861b-bb4ad2bbda15)
Verifying the PostgreSQL


# Step-3
Installing yarn 

- npm install --global yarn   or

- choco install yarn

![image](https://github.com/user-attachments/assets/b1c4a327-c4be-4a86-b47b-f925ef108442)
we can see the version of the yarn i.e. 1.22.22



# Step-4
Setting up and running the medusa

After the successful installation of the previous ones  hit this command

- yarn global add @medusajs/medusa-cli


You can create your own project using the following commands
-	medusa new my-medusa-store
-	npx @medusajs/medusa-cli new

OR

- 	yarn create medusa-app


![image](https://github.com/user-attachments/assets/e36a4a33-7c36-4c40-b2ad-fe185335357e)

Here, we creating the our first medusa app Fill up the database details clearly and you can create the app successfully.



![image](https://github.com/user-attachments/assets/d2e6044d-a6bf-4464-a378-26887cfb8a71)

While creating an application you can see the some useful packages are installing while creating an app



![image](https://github.com/user-attachments/assets/10988ba8-18d5-4144-83d3-a78d4ccd1669)
After creating an application you can see the database is created successfully.



![image](https://github.com/user-attachments/assets/7967c90f-47d5-4d47-b3e9-690ab65b7e13)
Here, we can see that our projects automatically get created.





Troubleshooting guide
https://docs.medusajs.com/troubleshooting/cli-installation-errors

