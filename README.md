# Active Directory Administration Lab

## 🎬 Watch Me Build This Lab

https://youtu.be/VdbJw3IN_8U

---

## Overview

This project demonstrates the deployment and administration of a Windows Server Active Directory environment. The lab simulates common Help Desk and System Administrator tasks including user management, Organizational Units (OUs), security groups, Group Policy Objects (GPOs), password policies, account lockout policies, and PowerShell verification.

---

## Lab Environment

- Windows Server 2022
- Active Directory Domain Services (AD DS)
- Active Directory Users and Computers
- Group Policy Management
- Windows PowerShell
- Virtual Machine

---

## Lab Architecture

<img width="1891" height="1891" alt="Lab 1 diagram" src="https://github.com/user-attachments/assets/9574d70d-2413-48aa-97f5-c2ceba78db39" />

---

## Project Walkthrough

### Step 1 – Configure Active Directory
I began by provisioning a Windows Server 2022 virtual machine in a virtualized environment. After completing the initial operating system configuration, I assigned the server a static IP address to ensure reliable communication for Active Directory and DNS services.

Next, I installed the Active Directory Domain Services (AD DS) role through Server Manager using the Add Roles and Features Wizard. During installation, the required management tools were also installed automatically.

Once AD DS was installed, I promoted the server to a Domain Controller by selecting "Promote this server to a domain controller." I created a new Active Directory forest using the domain name lab.local

### Step 2 – Create Organizational Units (OUs)

After successfully promoting the Windows Server to a Domain Controller and creating the lab.local domain, I launched Active Directory Users and Computers (ADUC) to begin organizing the directory.

Within the lab.local domain, I created four Organizational Units to represent different departments within a simulated business environment. these four orgainizations are IT, Human Resurces,Finance,sales. Having this structure orgainizes the evironemnt similar to how an orgainization seperates departments making it easier to manage.
### Step 3 – Create User Accounts

After creating the Organizational Units, I used Active Directory Users and Computers (ADUC) to create individual user accounts for each department. Each user account was placed into its corresponding Organizational Unit to maintain a logical directory structure and accurately reflect a real-world organizational hierarchy.
### Step 4 – Create Security Groups

After creating the user accounts, I used Active Directory Users and Computers (ADUC) to create security groups for each department within the domain. These groups were designed to represent common organizational roles and provide a centralized method for managing user permissions. The security groups created in this lab included IT_Admins, HR_Users, Finance_Users, and Sales_Users, with each group corresponding to its respective department. After creating the groups, I assigned the appropriate users to each one, demonstrating how Active Directory uses group-based management effectively.
### Step 5 – Configure Group Policy

After creating the Organizational Units, user accounts, and security groups, I opened the Group Policy Management Console (GPMC) to create and configure a new Group Policy Object for the domain. The policy was linked to the appropriate Active Directory container so that the configured settings would automatically apply to users within the domain.

Within the Group Policy Management Editor, I navigated through the Computer Configuration settings to configure security policies that strengthen authentication and protect domain accounts. The policies I configured For this lab were

Password complexity requirements
Minimum password length
Password history enforcement
Maximum password age
Account lockout threshold
Account lockout duration
Reset account lockout counter

After configuring the policies, I verified that the Group Policy Object was successfully linked and ready to be applied to the Active Directory environment.

### Step 6 – Verify Using PowerShell
After completing the Active Directory configuration, I opened Windows PowerShell as an administrator on the domain controller. I then used Active Directory PowerShell cmdlets to confirm that the objects created earlier in the lab were present in the domain.

I used the following commands:
```powershell
Get-ADUser -Filter *
Get-ADGroup -Filter *
Get-ADOrganizationalUnit -Filter *
```


### Step 8 – Demonstrate User Administration

After verifying that the Active Directory environment was configured correctly, I demonstrated several user administration tasks using Active Directory Users and Computers (ADUC). These tasks simulated common responsibilities performed by IT administrators when managing employee accounts throughout their lifecycle.

For this demonstration, I selected an existing user account and performed administrative actions such as disabling and re-enabling the account. Disabling a user account prevents the user from authenticating to the domain while preserving their account information, group memberships, and permissions. Re-enabling the account restores access without requiring the account to be recreated.

I also reviewed user account properties, including logon information, group memberships, and organizational placement. This demonstrated how administrators can quickly view and manage user information from a centralized interface.

Throughout the demonstration, I showed how Active Directory Users and Computers provides administrators with an efficient way to manage domain users while maintaining consistency across the organization.
---

## Skills Demonstrated

- Active Directory Administration
- Windows Server Administration
- Organizational Unit Management
- User Management
- Security Groups
- Group Policy
- PowerShell
- Identity and Access Management (IAM)

---

## Conclusion

This lab provided hands-on experience performing common Active Directory administration tasks within a Windows Server environment.
