<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

<h1>osTicket - Post-Install Configuration</h1>
This tutorial outlines the post-install configuration of the open-source help desk ticketing system osTicket.<br />




<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- osTicket Admin/Agent Panel http://localhost/osTicket/scp/login.php
- osTicket Support Center for endusers http://localhost/osTicket

<h2>Operating Systems Used </h2>

- Windows 10</b> (21H2)

<h2>Post-Install Configuration Objectives</h2>

- Configure Roles (for grouping permissions)
- Configure Departments (Ticket Visibility, Help Desk vs SysAdmins, vs Networking)
- Configure Teams
- Allow anyone to create tickets
- Configure Agents (workers)
- Configure Users (customers)
- Configure SLA
- Configure Help Topics (For when users create a ticket)

<h2>Configuration Steps</h2>
1) Sign in to the virtual machine using Remote Desktop Connection with the public ip address**
<p>

![ip address](https://github.com/user-attachments/assets/6b56414b-1807-46e9-ad57-b2b68123fb90)


</p>
<p>

 



</p>
<br />


<p>

![RDP](https://github.com/user-attachments/assets/1bb43f38-8d14-40d8-b05d-a9513ab85f27)

</p>
<p>
</p>
<br />

Sign in to osTicket Admin/Agent Panel
<p>

![os login](https://github.com/user-attachments/assets/4f23c248-cdec-48be-b9d0-1e241a70cb38)

Username and Password is the same from the osTicket Basic Instillation 

 ![os info](https://github.com/user-attachments/assets/925cd202-f93b-4660-a419-a6f46b56580b)

</p>
<p>
</p>
<br />
<h2>Admin Panel</h2>

You will know that you are in the Admin Panel when it says "Agent Panel" in the top right corner.


![admin](https://github.com/user-attachments/assets/87d7b2dc-92c4-44b0-b826-5860d7b4f2d0)



Take note off the features we will be using in the Admin Panel.

"Agents" is where we will create Roles, Departments, Teams and Agents (workers).
![Agents](https://github.com/user-attachments/assets/eea25ba6-c57f-486e-a0b1-eba6614207b4)

  "Manage" is where we will create Help Topics.
   
   ![Manage](https://github.com/user-attachments/assets/85eba74b-2fef-4d72-9805-82b4d4c275e8)

Also settings

![settings](https://github.com/user-attachments/assets/6063a1c9-2c75-4c71-8331-465d8fd9c0c0)


<h2>Agent Panel</h2>

You will know that you are in the Agent Panel when it says "Admin Panel" in the top right corner.

![Agent Panel](https://github.com/user-attachments/assets/46692b70-4d0b-4316-8c72-2f79a2367507)

For this lab we will only create "Users" in the Agent Panel.

![users](https://github.com/user-attachments/assets/a862fc7a-9245-49cb-a4b4-2d995d5ff1bd)




*****Now let's complete our post-install configuration.****

2) Configure Roles (for grouping permissions)

*****Admin Panel -> Agents -> Roles -> Add New Role*****


Configuring Roles grants different levels of actions to whoever is assigned to that role.



Click Admin Panel






Type "Supreme Admin" in the blank field and add role.

![Supreme](https://github.com/user-attachments/assets/be1aa1bd-e295-4976-928f-64c4c55260b5)















Grant All Permissions and Add Role

Tickets

![permissions](https://github.com/user-attachments/assets/ad074dc0-cd04-4902-a73b-1b89431095d9)


Tasks

![tasks](https://github.com/user-attachments/assets/831acbef-b5ec-41c6-8514-e1e4f6048a2b)


3) Configure Departments

The department a person is assigned to will determine ticket visibility.

**Admin Panel -> Agents -> Departments -> Add New Department**



Title Department "SysAdmins", make it Top-Level and create

![SysAdmins](https://github.com/user-attachments/assets/be34a860-84fd-4ce6-a87b-1617e90b099a)

  ![Create dept](https://github.com/user-attachments/assets/6c41d7c4-206a-41be-8631-0a4cc7d96d67)




4) Configure Teams

Teams are groups of people from different departments that come together to handle various aspects of a business function.

****Admin Panel -> Agents -> Teams -> Add New Team***

We will pull Agents from different Departments later.




Title Team "Online Banking" and create.

![Create Team](https://github.com/user-attachments/assets/9112be0e-9182-4dec-b3d1-40db4e1e3627)



5) Allow anyone to create tickets

Endusers can create tickets without having an account.

***Admin Panel -> Settings -> User Settings***

Ensure "Registered Required" in unchecked.

![Required](https://github.com/user-attachments/assets/9ebb83a6-7c17-45f4-8c97-f44735bee611)






6) Configure Agents (workers)

**Admin Panel -> Agents -> Add New Agent**

Jane Doe (Dept: SysAdmins) 

These are mock employees so you can make up the contact info.


![jane](https://github.com/user-attachments/assets/4e965269-d166-4d33-8ffb-e23f4f859dea)


When creating the password, uncheck "Require password change at next login".

![password](https://github.com/user-attachments/assets/41e44e2c-6ec7-4634-86e9-f90e9ad87a68)


 username: jane

 password: Password2


 Add Jane to the SysAdmins Department and make her a Supreme Admin.

![Jane Dept](https://github.com/user-attachments/assets/5139db13-6887-493a-980c-faa7f91ec6df)



 Add Jane to the Online Banking Team and create.

 ![Jane team](https://github.com/user-attachments/assets/a98bc5a1-11ca-4e98-9bb7-365f4e8b897e)


**Admin Panel -> Agents -> Add New Agent**

![john](https://github.com/user-attachments/assets/f6c111c1-81b7-4f4b-9673-e822c15badc9)


John Doe (Dept: Support)

 username: john

 password: Password2

Add John to the Support Department and give him Limited Access.

![John Dept](https://github.com/user-attachments/assets/2bdc9cac-900c-442d-a8cb-b881a5f3acac)


Add John to the Level 1 Support Team and create.

![John team](https://github.com/user-attachments/assets/7ff27d6b-9ea7-4b34-a90c-ac1e6acfe7d6)


 
7) Configure Users (customers)

   These are end users who may report technical difficulties with products or services.

**Agent Panel -> Users -> Add User**

Karen

![ad user](https://github.com/user-attachments/assets/bbd357aa-7fbe-41bd-9e38-f4a7e578b43b)


8) Configure SLA

SLA stands for service level agreement. It refers to a document that outlines a commitment between a service provider and a client, including details of the service, the standards the provider must adhere to, and the metrics to measure the performance.

The SLA grace period is a specified amount of time before penalties are applied for failing to meet the SLA's standards.

An SLA schedule is a time frame that defines when a service level agreement (SLA) is in effect.



**Admin Panel -> Manage -> SLA -> Add New SLA Plan**

Sev-A (Grace Period: 1 hour, Schedule: 24/7)

![SLA A](https://github.com/user-attachments/assets/488e6401-7529-4a39-8e74-9448e4e06242)


Sev-B (Grace Period: 4 hours, Schedule: 24/7)

![SLA B](https://github.com/user-attachments/assets/4f44b432-a46d-4bff-b5e9-0006d8aff3db)


Sev-C (Grace Period: 8 hours, Business Hours)

![Sev C](https://github.com/user-attachments/assets/9b0021dd-d51f-447a-befd-7d0ab87c63ff)








Configure Users (customers)

Agent Panel -> Users -> Add New

![image](https://github.com/user-attachments/assets/1b7474f9-7880-4b86-b927-8d8244395e9a)

Configure SLA

Admin Panel -> Manage -> SLA- Add New SLA Plan

SLA stands for service level agreement. It refers to a document that outlines a commitment between a service provider and a client, including details of the service, the standards the provider must adhere to, and the metrics to measure the performance.

THe SLA grace period is a specified amount of time before penalties are applied for failing to meet the SLA's standards.

An SLA schedule is a time frame that defines when a service level agreement (SLA) is in effect.

Sev-A (Grace Period: 1 hour, Schedule: 24/7)

![image](https://github.com/user-attachments/assets/9ca9f9c1-4f29-4cb6-ac56-ca62a030de97)


Sev-B (Grace Period: 4 hours, Schedule: 24/7)

![image](https://github.com/user-attachments/assets/e12e1d30-101b-4152-9988-e75d079106e4)

Sev-C (Grace Period: 8 hours, Business Hours)

![image](https://github.com/user-attachments/assets/e2f405c1-7ffa-4c80-abc6-414db57ffd61)

Configure Help Topics (For when agents/users create a ticket)

How to categorize the issue

Admin Panel -> Manage -> Help Topics- Add New Help Topic

Business Critical Outage

![image](https://github.com/user-attachments/assets/88878752-51b3-439d-97c9-1e9689864409)


Personal Computer Issues

![image](https://github.com/user-attachments/assets/d70792be-26e5-41fb-8945-a8bf73adc622)


Equipment Request

![image](https://github.com/user-attachments/assets/8cea545f-2728-40d7-ae13-baf211515bed)


Password Reset

![image](https://github.com/user-attachments/assets/c1b4abc5-e305-43a8-98ad-7aa5cca6384f)


Other

![image](https://github.com/user-attachments/assets/f9fa40bf-7661-4bf3-8946-9739fc34d2dd)


And that is how an Admin configures systems that are designed to be used by employees at a company.






 
