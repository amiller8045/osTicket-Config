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
1) Sign in to the virtual machine using Remote Desktop Connection with the public ip address.
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

Admin Panel -> Agents -> Departments -> Add New Department



Title Department "SysAdmins", make it Top-Level and create

![SysAdmins](https://github.com/user-attachments/assets/be34a860-84fd-4ce6-a87b-1617e90b099a)

  ![Create dept](https://github.com/user-attachments/assets/6c41d7c4-206a-41be-8631-0a4cc7d96d67)




4) Configure Teams

Teams are groups of people from different departments that come together to handle various aspects of a business function.

Admin Panel -> Agents -> Teams 

We will pull Agents from different Departments later.

Click Teams and Add New Team



![Teams](https://github.com/user-attachments/assets/e24b3f4a-b777-4e81-aa3b-439942c71db9)


Title Team "Online Banking" and create

![Online Banking](https://github.com/user-attachments/assets/c8a256f0-9055-4fa6-a610-7115630d0f1c)


Allow anyone to create tickets

Endusers can create tickets without having an account

Admin Panel -> Settings -> User Settings

![image](https://github.com/user-attachments/assets/9abbb37b-3bb4-4ed4-ba22-18b96d5e281b)




UNCHECK: unregistered users can create tickets and Save changes

![image](https://github.com/user-attachments/assets/3d2d2ab5-878c-461c-b0bf-b0cd9c08e909)

Configure Agents (workers)

Admin Panel -> Agents -> Add New, Jane Doe

![image](https://github.com/user-attachments/assets/c9fd36ee-f59b-48cf-94f2-5e86309d8bde)


Fill out info for new Agent

![image](https://github.com/user-attachments/assets/cc543aa9-b4da-4e39-b816-d7c7a12f4a50)

Assign to SysAdmins Department as Supreme Admin

![image](https://github.com/user-attachments/assets/bdef5491-ad69-4033-bb3d-cab9ddcf8137)

Assign to Online Banking Team

![image](https://github.com/user-attachments/assets/0255c4a4-c9fb-4f5f-b4b2-d959d0a3427f)


Add Jane to the Online Banking Team

Admin Panel- Teams- Online Banking- Memebers- Select Agent

![image](https://github.com/user-attachments/assets/93a71821-0bea-43a9-a114-f386468abb43)


Add another Agent, John Doe, Support Department, Level 1 Support Team


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






 
