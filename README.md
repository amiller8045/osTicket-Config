<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

<h1>osTicket - Post-Install Configuration</h1>
This tutorial outlines the post-install configuration of the open-source help desk ticketing system osTicket.<br />




<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- osTicket Admin/Admin Panel http://localhost/osTicket/scp/login.php
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
Get Public IP address of osTicket Virtual Machine from Azure
<p>

![IP Address](https://github.com/user-attachments/assets/9dd4ebec-b527-440e-b4b0-22ceb390b0ae)


</p>
<p>

</p>
<br />
Use Remote Desktop to log into Virtual Machine

On your computer, search for "Remote Desktop Connection" and use the public IP address to connect to the Windows Virtual Machine.

<p>

![Remote Desktop](https://github.com/user-attachments/assets/5bed827d-84fb-4e99-aa9c-3c56dd290885)

</p>
<p>
</p>
<br />
Within Virtual Machine browse to osTicket login page and sign in

Use the credentials you created when installing the osTicket prereques

<p>

![osTicket Login](https://github.com/user-attachments/assets/313e69ed-e465-4ce0-9337-0b6bdac38282)


</p>
<p>
</p>
<br />
Configure Roles

Configuring Roles grants different levels of actions to whoever is assigned to that role.

Admin Panel -> Agents -> Roles

Notice that the top right corner will say "Agent Panel" indicating that you are in the Admin Panel

![Admin Panel](https://github.com/user-attachments/assets/853a619d-6199-463f-85e1-b3c27cc258fe)









![Agents](https://github.com/user-attachments/assets/5b71a2a9-d06f-41ae-a5ee-fc26c9ee29d0)

![Roles](https://github.com/user-attachments/assets/b134ba55-2afe-4760-b136-e7f07a63f310)








Add New Role

![Supreme Admin](https://github.com/user-attachments/assets/b281b76e-ee67-4663-a275-367ceb471fad)


Title Role "Supreme Admin"
![Supreme Admin](https://github.com/user-attachments/assets/992277b3-c498-4511-b89a-e7d62dfe85a6)



Grant All Permissions and Add Role

![ALL](https://github.com/user-attachments/assets/3f7a4136-08a0-4c82-9b5c-87f4fd5d2ea3)

![Permissions](https://github.com/user-attachments/assets/6208dbcb-7a58-4ebb-91c6-5b1c29dcb982)


Configure Departments

The department a person is assigned to will determine ticket visibility.
Admin Panel -> Agents -> Departments

![Departments](https://github.com/user-attachments/assets/93d64db4-a24b-4f63-851a-6bb50a04dcb2)

Title Department "SysAdmins" and create

![Create Department](https://github.com/user-attachments/assets/d817f0ed-bb83-43ec-861d-70e1b79e9d35)





Configure Teams

Teams are groups of people from different departments that come together to handle various aspects of a business function.

Admin Panel -> Agents -> Teams (Pull Agents from different Departments)
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






 
