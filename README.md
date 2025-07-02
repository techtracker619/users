# 🧑‍💻 Active Directory Lab: Create and Manage Users, Groups, and Organizational Units (OUs)

This beginner-friendly lab walks you through the core Active Directory tasks every IT administrator should know — setting up Organizational Units (OUs), creating user accounts, building groups, and managing memberships. Ideal for homelab learners and IT newcomers.

---

## 🧠 Lab Objectives

- Build an OU structure to organize departments
- Create Active Directory users (GUI & PowerShell methods)
- Create security groups and add members
- Prepare folder permissions (NTFS/share) based on groups


---

## 🖥️ Lab Prerequisites

- Windows Server 2019 or later installed
- Active Directory Domain Services (AD DS) installed & configured
- Domain controller setup and running
- RSAT tools if working from a remote machine

---

## 🗂️ Step 1: Create OU (Organizational Units)

1. Open **Active Directory Users and Computers** (`dsa.msc`)
2. Right-click on your domain > **New** > **Organizational Unit**
3. Name it `Company` or something relevant
4. Inside `Company`, create sub-OUs:
   - IT
   - HR
   - Finance

![imagealt[](](https://github.com/techtracker619/users/blob/004bc9ce11d6c81f76a7de5f3202f1397af89d26/screenshots/VirtualBox_AC-DC-SERVER_24_06_2025_01_03_54.png)
![imagealt](

---

## 👤 Step 2: Create Users

### Method 1: Using the GUI

1. Right-click on the `IT` OU > **New** > **User**
2. Fill out:
   - First name: `John`
   - Last name: `Smith`
   - Username: `jsmith`
   - Password: `P@ssw0rd!`
3. Complete the wizard and enable the account

🧠 Repeat this step for each user you want to create.

### Method 2: Using PowerShell (script added later)

_This will be added in the scripting section._

---

## 👥 Step 3: Create Groups

1. Inside the `IT` OU:
   - Right-click > **New** > **Group**
   - Name it `IT_Support`
   - Group scope: **Global**
   - Group type: **Security**
2. Click OK

🧠 You can create more groups like `HR_Admins`, `Finance_ReadOnly`, etc.

---

## ➕ Step 4: Add Users to Groups

1. Double-click on the group (e.g., `IT_Support`)
2. Go to the **Members** tab
3. Click **Add**, enter the user’s name (e.g., `jsmith`), and confirm

✅ Best practice: Assign permissions to groups, not individuals.

---

## 📂 Step 5: Optional — Prepare Folder Permissions

1. On the file server, create a new folder (e.g., `\\ServerName\IT_Share`)
2. Right-click > **Properties** > **Security** tab
3. Add your AD group (`IT_Support`) and assign:
   - Modify
   - Read & execute
   - List folder contents

4. Go to the **Sharing** tab > Advanced Sharing > Set permissions accordingly

---

## 📸 Screenshots to Include

> 📁 Create a `screenshots/` folder in this repo and upload these

| Step | Screenshot Description |
|------|------------------------|
| OU Structure | Show your OU layout (Company > IT/HR/Finance) |
| Create User GUI | Wizard screen creating `John Smith` |
| Group Creation | Properties of your `IT_Support` group |
| Group Membership | Member tab showing users added |
| Folder Permissions | NTFS permissions with group added |
| Optional: PowerShell | AD user or group creation script run |

---

## 🧠 Summary

✅ By completing this lab, you’ve practiced:

- AD object organization
- User and group provisioning
- Access control fundamentals
- GUI and scripting foundations (coming soon)

---


---

## 📎 Related Labs

- [Local Active Directory Lab Setup (VirtualBox + Server 2019)](../Local_AD_Lab_Setup/README.md)
- [Group Policy Object (GPO) Lab](../GPO_Lab/README.md)

---

## 🤝 Author

Anthony Jenkins  
Follow for more labs on AD, Cybersecurity, and Systems Administration

---

