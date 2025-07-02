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
![imagealt](https://github.com/techtracker619/users/blob/bd7d63fb3c4325fa18b8067b4f26cec2d426ec86/screenshots/VirtualBox_AC-DC-SERVER_24_06_2025_01_04_28.png)
![imagealt](https://github.com/techtracker619/users/blob/2f29fea433c5310273c8f0409c0c3f930f49f670/screenshots/VirtualBox_AC-DC-SERVER_24_06_2025_01_06_53.png)

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

![imagealt](https://github.com/techtracker619/users/blob/899da3f7fb4c7d28002e5f799e17cb2b020e4387/screenshots/VirtualBox_AC-DC-SERVER_24_06_2025_01_08_51.png)
![imagealt](https://github.com/techtracker619/users/blob/522b9423acaf86a6273ccaee78154ef2efb244e4/screenshots/VirtualBox_AC-DC-SERVER_24_06_2025_01_10_34.png)
![imagealt](https://github.com/techtracker619/users/blob/6653091b6dec7719924d0cd4ee804bab4cb0220d/screenshots/VirtualBox_AC-DC-SERVER_24_06_2025_01_10_45.png)



---

## 👥 Step 3: Create Groups

1. Inside the `IT` OU:
   - Right-click > **New** > **Group**
   - Name it `IT_Support`
   - Group scope: **Global**
   - Group type: **Security**
2. Click OK

🧠 You can create more groups like `HR_Admins`, `Finance_ReadOnly`, etc.

![imagealt](https://github.com/techtracker619/users/blob/f650bf97f641e640ac079ee3a6580ba03113e337/screenshots/VirtualBox_AC-DC-SERVER_24_06_2025_01_16_48.png)


---

## ➕ Step 4: Add Users to Groups

1. Double-click on the group (e.g., `IT_Support`)
2. Go to the **Members** tab
3. Click **Add**, enter the user’s name (e.g., `jsmith`), and confirm

✅ Best practice: Assign permissions to groups, not individuals.

![imagealt](https://github.com/techtracker619/users/blob/42a82daaa371c6f8f27a2e5a0fe822f80b953657/screenshots/VirtualBox_AC-DC-SERVER_24_06_2025_17_58_06.png)

---

## 🔐 Group Policy Management (GPO) – GUI Only

#### 🧭 Step 5: Open Group Policy Management
- Server Manager → Tools → **Group Policy Management**

![imagealt](https://github.com/techtracker619/users/blob/1fcc623acd9b8fb2baaedd7b2daa99ac14a57d2d/screenshots/VirtualBox_AC-DC-SERVER_24_06_2025_20_33_06.png)

---

#### 📁 Step 6: Create New GPO
- Right-click **Group Policy Objects** → **New**
- Name it: `SecurityPolicy`

![imagealt](https://github.com/techtracker619/users/blob/73f6c77456ce64715653e0a65c5efd0f50d495ab/screenshots/VirtualBox_AC-DC-SERVER_24_06_2025_20_41_22.png)
![imagealt](https://github.com/techtracker619/users/blob/a6e259a6aa383444f7911b0713d1b6ebd2cd5072/screenshots/VirtualBox_AC-DC-SERVER_24_06_2025_20_41_59.png)

---

#### 🛠️ Step 7: Edit the GPO
- Right-click `SecurityPolicy` → **Edit**

![imagealt](https://github.com/techtracker619/users/blob/8c203e342b6d5d8f7ad3c02582130469529de09c/screenshots/VirtualBox_AC-DC-SERVER_24_06_2025_21_48_55.png)


---

#### 🔐 Step 8: Set Password Policy
- Navigate to:  
  `Computer Configuration > Policies > Windows Settings > Security Settings > Account Policies > Password Policy`
- Double-click **Minimum password age**
- Check **Define this policy** and set to **60 days**
![imagealt](https://github.com/techtracker619/users/blob/57c19313aeca4a7318f257fa76150b0abe0f286a/screenshots/VirtualBox_AC-DC-SERVER_24_06_2025_21_51_48.png)
---

#### 🔗 Step 9: Link GPO to Domain
- Right-click your domain (e.g., `mylab.local`) → **Link an Existing GPO**
- Select `SecurityPolicy` → Click **OK**

📸 Screenshot: `link-gpo-to-ou.png`

---

---


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

