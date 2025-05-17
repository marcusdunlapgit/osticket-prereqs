<p align="center">
  <img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

<h1 align="center">osTicket - Prerequisites and Installation Guide</h1>

This tutorial outlines the full setup of the open-source help desk ticketing system **osTicket** on a Windows 10 virtual machine in Microsoft Azure.

---

## 📺 Video Demonstration

- ### [YouTube: How To Install osTicket with Prerequisites](https://www.youtube.com)

---

## 💻 Environments and Technologies Used

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop Protocol (RDP)
- Internet Information Services (IIS)
- PHP, MySQL, HeidiSQL
- Windows 10 Pro (21H2)

---

## 🧰 List of Prerequisites

Before starting, ensure you have the following:

- Azure Subscription
- Windows 10 Virtual Machine with at least 4 vCPUs
- RDP access to the VM
- [osTicket-Installation-Files.zip](https://drive.google.com/drive/u/0/folders/1APMfNyfNzcxZC6EzdaNfdZsUwxWYChf6) (include your GitHub raw link here)
- Internet access inside the Virtual Machine

---

## ⚙️ Installation Steps

### 🔹 Step 1: Create and Connect to the Azure VM

1. Create a **Windows 10** VM on Azure with **4 vCPUs**.
2. Use **Remote Desktop (RDP)** to log into the VM.

<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Step 1 Screenshot"/>

---

### 🔹 Step 2: Prepare Installation Files

- Download `osTicket-Installation-Files.zip` to the VM desktop.
- Extract the contents if necessary — the folder should be named: `osTicket-Installation-Files`.

<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Step 2 Screenshot"/>

---

### 🔹 Step 3: Install IIS with CGI

- Go to `Control Panel` → `Programs` → `Turn Windows features on or off`.
- Enable:
  - ✅ **Internet Information Services**
  - ✅ **World Wide Web Services**
    - ✅ **Application Development Features** → ✅ **CGI**

<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Step 3 Screenshot"/>

---

### 🔹 Step 4: Install Required Components (DO NOT INSTALL ALL AT ONCE. PLEASE FOLLOW ALONG)

- Install **PHP Manager for IIS**
- Install **IIS Rewrite Module**
- Create `C:\PHP`
- Extract **PHP 7.3.8** to `C:\PHP`
- Install **VC++ Redistributable**
- Install **MySQL 5.5.62**

<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Step 4 Screenshot"/>

---

### 🔹 Step 5: Configure PHP in IIS

- Open **IIS Manager**
- Use **PHP Manager** to register: `C:\PHP\php-cgi.exe`
- Restart IIS

<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Step 5 Screenshot"/>

---

### 🔹 Step 6: Install osTicket

- Unzip `osTicket-v1.15.8.zip`
- Copy the `upload` folder to `C:\inetpub\wwwroot` and rename it to `osTicket`
- Restart IIS again

<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Step 6 Screenshot"/>

---

### 🔹 Step 7: Browse osTicket Installer

- In IIS, go to Sites → Default Web Site → osTicket
- Click `Browse *:80` to open osTicket in your browser

<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Step 7 Screenshot"/>

---

### 🔹 Step 8: Enable PHP Extensions

- Go to PHP Manager → “Enable or disable an extension”
- Enable:
  - `php_imap.dll`
  - `php_intl.dll`
  - `php_opcache.dll`

<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Step 8 Screenshot"/>

---

### 🔹 Step 9: Configure osTicket

- Rename `ost-sampleconfig.php` to `ost-config.php`
- Assign full control permissions to `Everyone`

<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Step 9 Screenshot"/>

---

### 🔹 Step 10: Fill Out Help Desk Information

- Helpdesk Name: **Marcus Help Desk**
- Default Email: `marcusdunlap.contact@gmail.com`
- Admin Account:
  - First Name: Marcus
  - Last Name: Dunlap
  - Email: `me@marcusdunlap.tech`
  - Username: `adminuser`
  - Password: `Password1`

<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Step 10 Screenshot"/>

---

### 🔹 Step 11: Create osTicket Database with HeidiSQL

- Launch **HeidiSQL**
- Connect using:
  - Username: `root`
  - Password: `root`
- Create a database named `osTicket`

<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Step 11 Screenshot"/>

---

### 🔹 Step 12: Finish Setup in Browser

- MySQL Database: `osTicket`
- MySQL Username: `root`
- MySQL Password: `root`
- Click `Install Now!`

<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Step 12 Screenshot"/>

---

## ✅ Completion

🎉 Congratulations! osTicket is now successfully installed and configured on your Azure Windows VM.

---

## 📝 Author

**Marcus Dunlap**  
📧 [marcusdunlap.contact@gmail.com](mailto:marcusdunlap.contact@gmail.com)

