# Complete Active Directory Setup and Configuration with enterprise level simulation

<p align="center">
<img src="https://i.imgur.com/pU5A58S.png" alt="Microsoft Active Directory Logo"/>
</p>

<h1>On-premises Active Directory Deployed in the Cloud (Azure)</h1>

Active Directory on Azure – Project Overview

This project showcases my hands-on experience designing and deploying an Active Directory (AD) environment on a Microsoft Azure virtual machine (VM). 

I created this project to deepen my understanding of enterprise-level identity and access management, as well as to simulate real-world IT infrastructure scenarios used in corporate environments.

Why I Built This Project?

As part of my journey to strengthen my skills in system administration, cloud infrastructure, and network security, I wanted to:

- Gain practical experience with Windows Server roles, particularly Active Directory Domain Services (AD DS).

- Learn how to provision and configure virtual machines in Azure.

- Simulate a realistic IT environment for centralized user management and authentication.

- Demonstrate my ability to build and manage cloud-hosted infrastructure from scratch.


<h1>Skills Demonstrated</h1>

_<b>1.) Microsoft Azure</b>_

- VM provisioning and network setup (vNets, NSGs)

- Remote administration via RDP

- Windows Server 2019/2022

_<b> 2.) Installing and configuring Active Directory Domain Services (AD DS)</b>_

- Creating and managing users, groups, and OUs

- Implementing Group Policy Objects (GPOs) for policy control

_<b> 3.) Networking Fundamentals </b>_

- DNS configuration for domain resolution

- Domain joining and trust relationships

_<b> 4.) Security and Access Management</b>_

- Role-based access control (RBAC)

- Centralized identity management

_<b> 5.) Documentation and Automation</b>_

- PowerShell scripting for user/group creation

<br />

<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Active Directory Domain Services
- PowerShell

<h2>Operating Systems Used </h2>

- Windows Server 2022
- Windows 10 (21H2)

<h2>High-Level Deployment and Configuration Steps</h2>

- Step 1: Setup and configure Microsoft Azure virtual machines and virtual network
- Step 2: Setup Active Directory and configure objects 
- Step 3: Use Windows Powershell commands to create users
- Step 4: Setup client computer and configure DNS settings
- Step 5: Implement Group Policy Objects

<h2>Step 1: Setting up Domain Controller on Windows Server</h2>

_<strong> 1.) Deploy Azure virtual machine with Windows Server for Domain Controller </strong>_

<p>
To simulate a real-world enterprise environment, I deployed a Windows Server virtual machine on Microsoft Azure and configured it as an Active Directory Domain Controller. This setup allowed me to gain hands-on experience with core infrastructure technologies that are essential in corporate IT environments. 
</p>

AZURE VIRTUAL MACHINE WITH WINDOWS SERVER (WILL BE USED TO HOST ACTIVE DIRECTORY AS A DOMAIN CONTROLLER)
<p>
<img width="2354" height="1081" alt="Screenshot 2025-08-06 194325" src="https://github.com/user-attachments/assets/07e39cec-3537-4a4e-8296-2356c3703011" />
</p>

THE SERVER WAS PROMOTED TO ACTIVE DIRECTORY DOMAIN CONTROLLER AND SAMPLEDOMAIN.COM WAS CREATED AS THE DOMAIN NAME
<p>
<img width="2361" height="951" alt="Screenshot 2025-08-06 195916" src="https://github.com/user-attachments/assets/c780ae56-2bab-4a44-baf0-564389cd8a85" />
</p>

<br />

<h2>Step 2: Setup Active Directory and configure objects (Users, computers, groups)</h2>

_<strong> 1.) Create new Containers and Organizatinal Units with Active Directory Objects </strong>_

<p>
As the next step in building a functional and realistic Active Directory environment, I created a structured hierarchy of Organizational Units (OUs), along with sample users and computer accounts. This was done to simulate how real organizations manage identity, access, and administrative boundaries at scale. 
</p>

Sample Active Directory Objects were created
<p>
<img width="1056" height="950" alt="image" src="https://github.com/user-attachments/assets/c2495a36-0645-4bb2-8c9d-f90d63589eb4" />
</p>

<br />

<h2>Step 3: Use Windows Powershell commands to create users</h2>

_<strong> 1.) The new random users will be added to the _EMPLOYEES organizational unit. </strong>_

<p>
To simulate a real-world enterprise environment with a scalable user base, I automated the creation of random test user accounts using a Windows PowerShell script and placed them within a dedicated Organizational Unit named _EMPLOYEES which can be later used to apply group policy objects. 
</p>

Windows Powershell script used to create 100 random users inside Domain Controller
<p>
<img width="1679" height="1034" alt="Screenshot 2025-08-06 201508" src="https://github.com/user-attachments/assets/901a0002-f7b3-4edd-bfa0-ee1b24e74bdb" />
</p>

The users were added to the Organzational Unit named _EMPLOYEES
<p>
<img width="1265" height="1043" alt="Screenshot 2025-08-06 201628" src="https://github.com/user-attachments/assets/62593c91-7ff2-4ba3-9708-62efb76f8eab" />
</p>

<br />

<h2> Step 4: Setup client computer and configure DNS settings</h2>

_<strong> A new virtual machine will be created in Azure to simulate a client computer in the domain with the appropriate DNS settings </strong>_

<p>
As part of my Active Directory project, I created a client computer and configured its DNS settings to simulate a real-world user environment. The purpose of this setup was to demonstrate how a typical end-user machine connects and interacts within a domain-controlled network.

By manually pointing the client computer's DNS to the domain controller's IP address, I ensured proper name resolution for domain services. This step was essential for the client to locate and authenticate with the domain controller during the domain join process. Successfully joining the domain allowed me to test user logins, group policy applications, and domain-based resource access—all critical aspects of managing a secure and centralized IT infrastructure. 
</p>

New virtual machine created to simualte a computer on the domain for the users
<p>
<img width="2458" height="1084" alt="Screenshot 2025-08-07 095919" src="https://github.com/user-attachments/assets/f34da18a-3339-4ca6-ab06-4d800e5fc64c" />
</p>

The IP address of the client DNS server is set to the IP address of the Domain Controller
<p>
<img width="1471" height="962" alt="Screenshot 2025-08-07 100031" src="https://github.com/user-attachments/assets/9f989c8e-1229-4d7f-b049-7359e0d3b111" />
</p>

The client computer is added to the domain in system settings
<p>
<img width="543" height="564" alt="Screenshot 2025-08-07 100944" src="https://github.com/user-attachments/assets/cd0866b1-1236-4b4b-bb61-d316d5d1a57f" />
</p>

<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />
