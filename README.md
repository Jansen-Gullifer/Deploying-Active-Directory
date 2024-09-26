# Deploying-Active-Directory
<p align="center">
<img src="https://i.imgur.com/pU5A58S.png" alt="Microsoft Active Directory Logo"/>
</p>

<h1>On-premises Active Directory Deployed in the Cloud (Azure)</h1>
This tutorial outlines the implementation of on-premises Active Directory within Azure Virtual Machines.<br />


<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Active Directory Domain Services
- PowerShell

<h2>Operating Systems Used </h2>

- Windows Server 2022
- Windows 10 (21H2)

<h2>High-Level Deployment and Configuration Steps</h2>

- Install Active Directory
- Create a new user account named Jane Doe with the username jane_admin
- Configure Remote Desktop 
- Turn on the DC-1 and Client-1 VMs in the Azure Portal
- Log into DC-1 as jane_admin
- Open Active Directory Users and Computers (ADUC) and check the _EMPLOYEES OU for the new accounts

<h2>Deployment and Configuration Steps</h2>

<p>
  Part 1: Install Active Directory and Set Up Domain Admin
Install Active Directory:

1. Log into DC-1 and install Active Directory Domain Services.
Promote the server to a Domain Controller, creating a new forest with the domain name mydomain.com.
Restart the server and log back in as mydomain.com\labuser.
Create Organizational Units (OUs):

2. Open Active Directory Users and Computers (ADUC).
Create an Organizational Unit (OU) named _EMPLOYEES.
Create another OU named _ADMINS.
Create Domain Admin User:

3. Create a new user account named Jane Doe with the username jane_admin and password Cyberlab123!.
Add jane_admin to the Domain Admins Security Group.
Log out and then log back in as mydomain.com\jane_admin, using this account for administrative tasks moving forward.
</p>
<p>

![image](https://github.com/user-attachments/assets/d75f9135-d56f-4c3f-8c68-5974ec12c269)


</p>
<br />
  Part 2: Configure Remote Desktop and Create Additional Users
Set Up Remote Desktop on Client-1:

1. Turn on the DC-1 and Client-1 VMs in the Azure Portal.
Log into Client-1 as mydomain.com\jane_admin.
Open System Properties and go to the Remote Desktop tab.
Allow Domain Users access to Remote Desktop.
You can now log into Client-1 as a normal user.
Create Additional Users via PowerShell:

2. Log into DC-1 as jane_admin.
Open PowerShell ISE as an administrator.
Create a new file and paste the user creation script into it.
Run the script to create multiple user accounts.
Verify User Creation and Log In:

3. Open Active Directory Users and Computers (ADUC) and check the _EMPLOYEES OU for the new accounts.
Attempt to log into Client-1 with one of the newly created accounts (use the password specified in the script).

![image](https://github.com/user-attachments/assets/031def50-b5e8-412b-9ccd-4f291c472274)
