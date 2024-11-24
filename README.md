<p align="center">
<img src="(ttps://i.imgur.com/OMlBqhu.jpeg" height="40%" width="60%" alt="osTicket"/>
</p>

# osTicket - Prerequisites and Installation

This tutorial provides a step-by-step guide to setting up osTicket, an open-source help desk ticketing system.

## Environments and Technologies Used
- **Microsoft Azure** (for hosting virtual machines)  
- **Remote Desktop** (to access and manage virtual machines)  
- **Internet Information Services (IIS)** (to host the osTicket web application)  

## Operating Systems Used
- **Windows 10 (21H2)**  

## List of Prerequisites
- Enable **Internet Information Services (IIS)**.  
- Install **Microsoft Web Platform Installer**.  
- Install **MySQL 5.5**.  
- Install all **x86 PHP versions** up to v7.3.  
- Install **C++ Redistributable**.  
- Install **PHP Manager**.  
- Install **osTicket v1.15.8**.  
- Configure and restart IIS.  
- Enable required PHP extensions.  
- Verify installation by refreshing the osTicket site.  
- Perform cleanup tasks to optimize performance.  

## Installation Steps

### Step 1: Enable Internet Information Services (IIS)  
<p align="center">
<img src="" height="40%" width="60%" alt="Step 1 Image"/>
</p>  
<br>  

1. Open the **Control Panel** on your computer.  
2. Navigate to **Programs**, then click **Turn Windows Features On or Off**.  
3. Select the checkbox for **Internet Information Services (IIS)** and click **OK**.  
4. Download and install the **Microsoft Web Platform Installer** to simplify further installations.  
&nbsp;  

---

### Step 2: Install MySQL and PHP  
<p align="center">
<img src="" height="40%" width="60%" alt="Step 2 Image"/>
</p>  
<br>  

1. Open the **Web Platform Installer**.  
2. Search for and install **MySQL 5.5**.  
3. Search for and install all **x86 PHP versions** up to v7.3.  
4. During installation, create a username and password for MySQL.  
5. If any tools fail to install, manually download and install:  
   - **C++ Redistributable**  
   - **PHP Manager** (versions 7.3.8 and 1.5.0).  
&nbsp;  

---

### Step 3: Install osTicket v1.15.8  
<p align="center">
<img src="" height="40%" width="60%" alt="Step 3 Image"/>
</p>  
<br>  

1. Download osTicket v1.15.8 and extract the ZIP file.  
2. Copy the extracted folder into the IIS **wwwroot** directory:  
   `C:\inetpub\wwwroot`.  
3. Rename the folder from **upload** to **osTicket**.  
&nbsp;  

---

### Step 4: Restart IIS and Configure Extensions  
<p align="center">
<img src="" height="40%" width="60%" alt="Step 4 Image"/>
</p>  
<br>  

1. Open **IIS Manager**.  
2. Stop and restart the web server:  
   Navigate to **Sites > osTicket > Browse 80**, then stop and restart.  
3. Enable the following PHP extensions in IIS:  
   - `php_imap.dll`  
   - `php_intl.dll`  
   - `php_opcache.dll`  
4. Refresh the osTicket site in your browser to verify changes.  
&nbsp;  

---

### Step 5: Finalize Configuration  
<p align="center">
<img src="" height="40%" width="60%" alt="Step 5 Image"/>
</p>  
<br>  

1. Rename the file `ost-sampleconfig.php` to `ost-config.php` in:  
   `C:\inetpub\wwwroot\osTicket\include`.  
2. Update file permissions for `ost-config.php`:  
   - Right-click the file, select **Properties > Advanced > Disable Inheritance**.  
   - Grant **Full Access** to "Everyone" and click **Apply**.  
3. Install **HeidiSQL** to connect MySQL to osTicket.  
4. Use HeidiSQL to create a new database named **osTicket**, using the MySQL credentials.  
5. In your browser, open the osTicket installer and fill out:  
   - **System Settings**  
   - **Admin User**  
   - **Database Settings**  
   - Click **Install Now**.  
&nbsp;  

---

### Step 6: Clean Up Files  
<p align="center">
<img src="" height="40%" width="60%" alt="Step 6 Image"/>
</p>  
<br>  

1. Delete the **setup** folder from:  
   `C:\inetpub\wwwroot\osTicket`.  
2. Update `ost-config.php` permissions:  
   - Allow only **Read & Execute** for "Everyone".  
   - Deselect other permissions and click **Apply**.  
&nbsp;  

---

> **You have successfully installed osTicket!**  
> For further assistance, refer to the official [osTicket Documentation](https://docs.osticket.com).

## FAQ
**Q: What should I do if installation fails?**  
A: Ensure all prerequisites are installed, including missing PHP extensions or C++ Redistributable.  

**Q: How do I access the osTicket admin panel?**  
A: Navigate to the osTicket URL in your browser and log in with the admin credentials you created during installation.  

---

## Conclusion
🎉 You’ve successfully set up osTicket! 🎉