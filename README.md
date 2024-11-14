# 2 The-Day-to-Day


This section focuses on practical, day-to-day IT support tasks and essential customer service skills.

- **[Working Os Tickets](The_Day_to_Day/01_Working_Tickets/)**
  - *[Exercise - Working Os Tickets](The_Day_to_Day/01_Working_Tickets/Exercise_Working_Tickets.md)*

- **[Common Issues](The_Day_to_Day/03_Common_Issues/)**
  - *[Exercise - Common Issues](The_Day_to_Day/03_Common_Issues/Exercise_Common_Issues.md)*

- **[Common Tools](The_Day_to_Day/05_Common_Tools/)**
  - *[Exercise - Common Tools](The_Day_to_Day/05_Common_Tools/Exercise_Common_Tools.md)*

- **[Customer Service & Soft Skills](The_Day_to_Day/07_Customer_Service_Soft_Skills/)**
  - *[Exercise - Customer Service & Soft Skills](The_Day_to_Day/07_Customer_Service_Soft_Skills/Exercise_Customer_Service_Soft_Skills.md)*



---

# osTicket Setup Project

![osTicket Installation](https://i.ytimg.com/vi/Olh1z-RNEhQ/maxresdefault.jpg)

<details>
<summary><strong>Technologies Used</strong></summary>

- **Microsoft Azure**
- **Remote Desktop**
- **Internet Information Services (IIS)**

</details>

<details>
<summary><strong>Operating Systems Used</strong></summary>

- **Windows 10**
- **Windows Server 2022**

</details>

<details>
<summary><strong>Definitions</strong></summary>

- **Localhost**: The loopback address (127.0.0.1), used for testing web applications, network configurations, and blocking malicious sites.
- **Internet Information Services (IIS)**: A web server application that supports various protocols (HTTP, HTTPS, FTP, etc.) and enables site management, application hosting, and performance monitoring.

</details>

---

## Prerequisites

<details>
<summary><strong>Set Up a Virtual Machine in Azure</strong></summary>

1. Log in to **Microsoft Azure**.
2. Go to **Virtual Machine** > **Create**.
3. Select **Zone 3** and choose **Windows 10** as the OS.
4. Set up a **username** and **password**, then click **Create**.
5. Copy the IP address of the VM and connect via **Remote Desktop**.
6. Log in using the specified username and password.
7. Open a browser within the VM to access the lab files needed for osTicket.

</details>

---

## Installing osTicket Files

<details>
<summary><strong>Download and Unzip osTicket</strong></summary>

1. Download the osTicket installation files and unzip them on the virtual machine.

</details>

<details>
<summary><strong>Enable IIS</strong></summary>

1. Open **Control Panel** > **Programs** > **Turn Windows features on or off**.
2. Select **World Wide Web Services** > **Application Development Features** > enable **CGI**.
3. Test the setup by entering **127.0.0.1** in the browser. A blue screen should confirm that IIS is running. If not, repeat the previous steps.

</details>

---

## Install Necessary Components

<details>
<summary><strong>Install PHP Manager and Rewrite Module</strong></summary>

1. Download and install **PHP Manager** and **Rewrite Module**.

</details>

<details>
<summary><strong>Create a PHP Directory</strong></summary>

1. Open **File Explorer** and create a new folder at **C:\PHP**.

</details>

<details>
<summary><strong>Unzip PHP</strong></summary>

1. Download PHP 7.3.8 and unzip the files into the **C:\PHP** directory.

</details>

<details>
<summary><strong>Install Visual C++ and MySQL</strong></summary>

1. Download and install **Visual C++**.
2. Download and install **MySQL**.

</details>

<details>
<summary><strong>Configure MySQL</strong></summary>

1. During installation, select **Typical Setup**.
2. Launch the MySQL configuration wizard, choose **Standard Configuration**.
3. Set up a **username** and **password** for MySQL access.

</details>

---

## Configuring IIS for osTicket

<details>
<summary><strong>Open IIS Manager</strong></summary>

1. Open **IIS Manager** with Administrator privileges.

</details>

<details>
<summary><strong>Register PHP in IIS</strong></summary>

1. Click on **PHP Manager** in IIS.
2. Select **Register new PHP version** and navigate to **php-cgi.exe** in **C:\PHP**.
3. Reload IIS.

</details>

<details>
<summary><strong>Set Up osTicket in IIS</strong></summary>

1. Unzip the osTicket files.
2. Move the **uploads** folder to **C:\inetpub\wwwroot** and rename it to **osTicket**.

</details>

<details>
<summary><strong>Launch osTicket</strong></summary>

1. Reload IIS.
2. In **IIS Manager**, right-click on **Default Web Site** > **Browse *:80**.
3. osTicket should now open in the browser. If not, check the previous steps for any issues.

</details>

---

## Finalizing osTicket Setup

<details>
<summary><strong>Enable Required PHP Extensions</strong></summary>

1. Enable the following PHP extensions:
   - **php_imap.dll**
   - **php_intl.dll**
   - **php_opcache.dll**
2. Refresh the osTicket setup page. All extension requirements should show green checks.
   
![Install Necessary Components for osTicket](https://www.atlantic.net/wp-content/uploads/2021/12/p1-7.png)

</details>
<details>

<summary><strong>Rename and Configure Configuration File</strong></summary>

1. Rename **ost-sampleconfig.php** in the osTicket folder to **ost-config.php**.
2. Right-click **ost-config.php**, go to **Properties** > **Security**, and allow **full access for Everyone**.

</details>

---

## Database Configuration

<details>
<summary><strong>Install and Configure HeidiSQL</strong></summary>

1. Download and install **HeidiSQL** from the osTicket installation files.
2. Open HeidiSQL and create a new session.
3. Log in using the MySQL username and password created earlier.
4. Connect to the session and create a database named **osTicket**.

</details>

<details>
<summary><strong>Complete osTicket Setup</strong></summary>

1. In the osTicket browser setup page, input the database information from HeidiSQL.
2. Fill out other required fields, like **Admin Username**, **Password**, and **Email**.
3. Click **Continue** to complete the setup.


</details>


![Configuring IIS for osTicket](https://osticketawesome.com/wp-content/uploads/2020/09/web-installer-directory4.gif)

---

## Completion

**Congratulations!** You have successfully installed osTicket. From here, you can:
- **Explore osTicket functionalities** for managing and resolving support tickets.
- **Learn administrative features** such as account setup and ticket prioritization.
