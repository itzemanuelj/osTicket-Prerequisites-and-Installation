<p align="center">
<img src="https://i.imgur.com/OMlBqhu.jpeg" height="40%" width="60%" alt="osTicket"/>
</p>

# osTicket - Prerequisites and Installation

This guide provides a step-by-step walkthrough for installing and configuring **osTicket**, an open-source help desk ticketing system.

## Environments and Technologies Used
- **Microsoft Azure** (Virtual Machines/Compute)
- **Microsoft Remote Desktop (RDP)**
- **Internet Information Services (IIS)**

## Operating Systems Used
- **Windows 10 Pro**

## Prerequisites
Before starting, ensure you have:
- Access to **Microsoft Azure** for creating a Virtual Machine (VM).
- **osTicket installation files** (available [here](https://drive.google.com/drive/u/0/folders/1APMfNyfNzcxZC6EzdaNfdZsUwxWYChf6)).
- **HeidiSQL** for database management.

## Installation Steps

### Step 1: Create a Virtual Machine on Azure
1. **Log into the Azure Portal**: [portal.azure.com](https://portal.azure.com).
2. Create a **Resource Group** named `osTicket`.
3. Create a **Virtual Machine (VM)** with:
   - **2-4 CPUs** (4 CPUs recommended).
   - Operating System: Windows 10.
###if you need link o azure vm setup###
4. **Connect to the VM**:
   - Use **Remote Desktop Protocol (RDP)** with the VM's public IPv4 address.
   - For Mac users, download [Microsoft Remote Desktop](https://apps.apple.com/us/app/microsoft-remote-desktop/id1295203466).

![1](https://i.imgur.com/dx0DlsD.png)
![2](https://i.imgur.com/6m3vMHu.png)
![3](https://i.imgur.com/xX25Ov5.png)
![3](https://i.imgur.com/u4ZCz1S.png)
<br>

### Step 2: Enable Internet Information Services (IIS)
type run to open powrshell type control
1. Open the **Control Panel** on your VM.
2. Navigate to: **Programs** > **Turn Windows Features On or Off**.
3. Enable **Internet Information Services (IIS)** by checking the box and clicking **OK**.

[1]()
[2]()
[3]()
<br>


### Step 3: Install Web Platform Installer
1. Download the **Web Platform Installer** from the provided [Google Drive link](https://drive.google.com/drive/u/0/folders/1APMfNyfNzcxZC6EzdaNfdZsUwxWYChf6).
2. Install and open the Web Platform Installer.

[1]()
[2]()
[3]()
<br>

### Step 4: Install MySQL and PHP
1. Using the **Web Platform Installer**:
   - Install **MySQL 5.5**.
   - Install all **x86 PHP versions** up to version 7.3.
2. Manually download and install the following if they fail:
   - **C++ Redistributable Package**.
   - **PHP Manager for IIS**.
   - **PHP 7.3.8**.

[1]()
[2]()
[3]()
<br>

### Step 5: Install osTicket
1. Download and extract the **osTicket installation files** from the provided link.
2. Copy the `upload` folder to `C:\inetpub\wwwroot`.
3. Rename the `upload` folder to **osTicket**.

[1]()
[2]()
[3]()
<br>


### Step 6: Configure IIS and Start osTicket
1. Open **IIS Manager** and restart the IIS server:
   - Navigate to: **Sites > Default > osTicket**.
   - On the right panel, click **Browse *.80** to open the osTicket web server in your browser.
2. Enable required PHP extensions:
   - In IIS Manager, navigate to **Sites > Default > osTicket > PHP Manager**.
   - Click **Enable or Disable Extensions** and enable:
     - `php_intl.dll`
     - `php_opcache.dll`
3. Refresh the osTicket site in your browser. The **Intl Extension** should now be enabled.

[1]()
[2]()
[3]()
<br>

### Step 7: Configure `ost-config.php`
1. Navigate to: `C:\inetpub\wwwroot\osTicket\include`.
2. Rename `ost-sampleconfig.php` to `ost-config.php`.
3. Assign permissions to `ost-config.php`:
   - Right-click the file, select **Properties > Security > Advanced > Disable Inheritance**.
   - Remove inherited permissions.
   - Add a new permission for **Everyone** with **Full Control**.

[1]()
[2]()
[3]()
<br>

### Step 8: Finalize osTicket Setup in Browser
1. In the osTicket web interface, complete the setup:
   - **Helpdesk Name**: Your preferred name.
   - **Default Email**: An email for receiving customer tickets.
2. Configure MySQL settings:
   - **Database Name**: `osTicket`
   - **Username**: `root`
   - **Password**: `Password1`
3. Click **Install Now!** to finalize the installation.

[1]()
[2]()
[3]()
<br>

### Step 9: Post-Installation Cleanup
1. Delete the `setup` folder:  
   `C:\inetpub\wwwroot\osTicket\setup`.
2. Set `ost-config.php` to **Read Only**:
   - Right-click the file, select **Properties > Security**.
   - Update permissions to allow only **Read & Execute** for Everyone.

[1]()
[2]()
[3]()
<br>

## Access osTicket
- **User Portal**: [http://localhost/osTicket](http://localhost/osTicket)
- **Admin Panel**: [http://localhost/osTicket/scp/login.php](http://localhost/osTicket/scp/login.php)

---

🎉 **Congratulations! You have successfully installed osTicket.** 🎉
