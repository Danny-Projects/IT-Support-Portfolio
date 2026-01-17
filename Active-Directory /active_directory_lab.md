# Active Directory User Account & Group Policy Troubleshooting Lab

## Lab Overview
This lab demonstrates the setup and administration of an Active Directory environment, including domain controller deployment, organizational unit (OU) structure, user and group management, domain joining, and Group Policy enforcement from both server and client perspectives.

---

## Environment
- Windows Server 2019 (Domain Controller)
- Windows 10 (Domain-joined client)
- VirtualBox Internal Network
- Domain: **lab.local**

---

## Objectives
- Install and configure Active Directory Domain Services
- Promote a server to Domain Controller
- Create organizational units (OUs)
- Create and manage domain users
- Create and assign security groups
- Join a Windows 10 client to the domain
- Apply and validate Group Policy restrictions

---

## Step-by-Step Implementation

### 1. Installed Active Directory Domain Services
During server role installation, Active Directory Domain Services was selected.

![Select server roles](https://github.com/Danny-Projects/IT-Support-Portfolio/blob/main/Active-Directory%20/screenshots/Select_server_roles(1).png)

---

### 2. Completed AD DS Installation
Installation completed successfully and required post-deployment configuration.

![AD DS installation complete](https://github.com/Danny-Projects/IT-Support-Portfolio/blob/main/Active-Directory%20/screenshots/installation_complete(2).png)

---

### 3. Promoted Server to Domain Controller
The server **DC01** was promoted to a Domain Controller.

![Promote server to domain controller](https://github.com/Danny-Projects/IT-Support-Portfolio/blob/main/Active-Directory%20/screenshots/promote_server(3).png)

---

### 4. Configured Directory Services Restore Mode (DSRM) Password
A DSRM password was configured as part of domain controller setup.

![DSRM password configuration](https://github.com/Danny-Projects/IT-Support-Portfolio/blob/main/Active-Directory%20/screenshots/password_set(4).png)

---

### 5. Domain Controller Configuration Completed
The server was successfully configured with the domain **lab.local**.

![Domain controller setup complete](https://github.com/Danny-Projects/IT-Support-Portfolio/blob/main/Active-Directory%20/screenshots/DC01_setup(5).png)

---

### 6. Verified Domain in Active Directory Users and Computers
The new domain **lab.local** was visible in ADUC.

![Domain visible in ADUC](https://github.com/Danny-Projects/IT-Support-Portfolio/blob/main/Active-Directory%20/screenshots/lab_local(6).png)

---

### 7. Created Organizational Units (OUs)
The following OUs were created:
- IT_Admins
- IT_Users
- Workstations

![Organizational units created](https://github.com/Danny-Projects/IT-Support-Portfolio/blob/main/Active-Directory%20/screenshots/OUs_created(7).png)

---

### 8. Created Domain User
A test domain user **John Doe** was created and placed inside the **IT_Users** OU.

![Domain user John Doe created](https://github.com/Danny-Projects/IT-Support-Portfolio/blob/main/Active-Directory%20/screenshots/Test_User_John_Doe(8).png)

---

### 9. Verified Domain Login from Windows 10 Client
The user successfully logged into the domain from the client machine.

![Domain login verified on Windows 10 client](https://github.com/Danny-Projects/IT-Support-Portfolio/blob/main/Active-Directory%20/screenshots/jdoe_win10(9).png)

---

### 10. Created Security Groups
Security groups were created under a structured OU hierarchy.

![Security groups created](https://github.com/Danny-Projects/IT-Support-Portfolio/blob/main/Active-Directory%20/screenshots/Security_Groups(10).png)

---

### 11. Added User to Security Group
John Doe was added to the **IT_Users** security group.

![User added to IT Users security group](https://github.com/Danny-Projects/IT-Support-Portfolio/blob/main/Active-Directory%20/screenshots/jdoe_groups(11).png)

---

### 12. Verified Group Membership via Command Line
Group membership was confirmed using command-line tools.

![Group membership verified via command line](https://github.com/Danny-Projects/IT-Support-Portfolio/blob/main/Active-Directory%20/screenshots/jdoe_cmd_groups(12).png)

---

### 13. Created Group Policy Object (GPO)
A Group Policy Object named **Restrict Control Panel** was created.

![Group Policy Object created](https://github.com/Danny-Projects/IT-Support-Portfolio/blob/main/Active-Directory%20/screenshots/GPO(13).png)

---

### 14. Updated Group Policy on Client
Group Policy was updated on the Windows 10 client using:
```cmd
gpupdate /force
```
![Group policy updated on client](https://github.com/Danny-Projects/IT-Support-Portfolio/blob/main/Active-Directory%20/screenshots/gpudpate(14).png)

---

### 15. Verified Policy Enforcement
Access to Control Panel was successfully restricted for the domain user.

![Control panel access denied by group policy](https://github.com/Danny-Projects/IT-Support-Portfolio/blob/main/Active-Directory%20/screenshots/error_control_panel(15).png)

---

## Results
- Active Directory successfully deployed
- Domain controller configured and operational
- Client machine joined to domain
- Users and groups managed through ADUC
- Group Policy successfully enforced at the user level

---

## Key Skills Demonstrated
- Active Directory Domain Services
- Domain Controller configuration
- Organizational Unit design
- User and group administration
- Domain join troubleshooting
- Group Policy creation and enforcement
- Client-side validation
