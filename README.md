# Active Directory Lab – Windows Server & Windows 10

## Project Overview
The purpose of this project is to build a virtual Active Directory (AD) environment for hands-on learning in network and system administration. The lab involves **Windows Server 2016** as a Domain Controller and **Windows 10** clients, with a focus on configuring AD services, managing users and groups, applying Group Policies, and controlling file share permissions.

This project simulates a small enterprise environment and demonstrates practical skills in network configuration, user management, and domain-based security controls.

---


**Components Involved:**
- **Windows Server 2016** – AD Domain Controller (DC), DNS, DHCP  
- **Windows 10** – Client machine (joined to the AD domain)  
- **Internal Network (VirtualBox Host-Only)** – Simulated LAN for AD communication  
- **Group Policies (GPOs)** – Password policies, account lockout policies  
- **File Shares** – Controlled access based on AD groups  



---


## Conclusion
This lab demonstrates the creation and configuration of a **Windows Server 2019 Active Directory environment** with domain-joined Windows 10 clients.  

**Skills demonstrated:**
- AD DS installation and configuration  
- DNS and DHCP setup  
- User and group management  
- Group Policy application for security enforcement  
- Controlled access to file shares  

This project strengthened my practical skills in **Windows Server administration**, **enterprise networking**, and **security best practices**.

---


## Walkthrough & Screenshots

**Installing Windows Server 2016**


![Starting installation](images/Screenshot%202025-11-20%20140134.png)
![Screenshot 2](images/Screenshot%202025-11-20%20140208.png)
![Screenshot 3](images/Screenshot%202025-11-20%20140319.png)
![Screenshot 4](images/Screenshot%202025-11-20%20140338.png)
![Screenshot 5](images/Screenshot%202025-11-20%20140358.png)
![Screenshot 6](images/Screenshot%202025-11-20%20140413.png)
![Screenshot 7](images/Screenshot%202025-11-20%20140431.png)
![Screenshot 9](images/Screenshot%202025-11-20%20140504.png)

**Renaming the server to AD-SERVER**

![](images/Screenshot%202025-11-20%20151227.png)

**Configuring a static IP on the server**
![](images/Screenshot%202025-11-20%20151548.png)

**Installing Windows 10**
![](images/Screenshot%202025-11-20%20170516.png)
![](images/Screenshot%202025-11-20%20170800.png)
![](images/Screenshot%202025-11-20%20170809.png)
![](images/Screenshot%202025-11-20%20170819.png)
![](images/Screenshot%202025-11-20%20170828.png)
![](images/Screenshot%202025-11-20%20170841.png)
![](images/Screenshot%202025-11-20%20170851.png)
![](images/Screenshot%202025-11-20%20170900.png)
![](images/Screenshot%202025-11-20%20170908.png)

**Renaming windows 10 machine**
![](images/Screenshot%202025-11-20%20172307.png)

**Configuring a static IP for Windows 10 Machine**
![](images/Screenshot%202025-11-20%20201614.png)

---
**Installing Active Directory Domain Services (AD DS)**

![](images/add%20roles%20and%20features.png)
![](images/choose%20role%20based%20installation.png)
![](images/select%20the%20server.png)
![](images/tick%20active%20directory%20domain%20services.png)
![](images/install.png)

---
**Promote Server to a Domain Controller**

![](images/promote.png)
![](images/forest.png)
![](images/password.png)
![](images/install2.png)

---
**Verify DNS is working**

DNS is critical. To check that it is working correctly I went to the command prompt typed in the command ipconfig /all and made sure that the preffered DNS = the server's own IP (192.168.1.10)
![](images/cmd.png)
![](images/ipconfigall.png)
![](images/dnsresults.png)

---
**Join the Windows 10 Machine to the Domain**

To do this, I went to System > Rename this PC (advanced). Then I clicked change, selected domain, entered the domain name (lab.local). Lastly I entered the domain admin credentials. The client then rebooted for changes to occur.

![](images/system.png)
![](images/renamepc.png)
![](images/change.png)
![](images/selectdomain.png)
![](images/admindetails.png)






