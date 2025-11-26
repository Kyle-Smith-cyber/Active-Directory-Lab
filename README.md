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

---

**Create AD Orginisational Unit (OU) structure**

![](images/Screenshot%202025-11-24%20121128.png)
![](images/Screenshot%202025-11-24%20121229.png)
![](images/Screenshot%202025-11-24%20121254.png)
![](images/Screenshot%202025-11-24%20121319.png)
![](images/Screenshot%202025-11-24%20121404.png)
![](images/Screenshot%202025-11-24%20121423.png)


**Moving The Windows 10 Machine into "Lab Computers"**
![](images/Screenshot%202025-11-24%20121516.png)


**Creating regular user accounts**

![](images/Screenshot%202025-11-24%20122224.png)
![](images/Screenshot%202025-11-24%20122503.png)
![](images/Screenshot%202025-11-24%20122547.png)
![](images/Screenshot%202025-11-24%20122628.png)
![](images/Screenshot%202025-11-24%20122717.png)



**Creating security groups**

![](images/Screenshot%202025-11-24%20123203.png)
![](images/Screenshot%202025-11-24%20123234.png)
![](images/Screenshot%202025-11-24%20123256.png)
![](images/Screenshot%202025-11-24%20123313.png)
![](images/Screenshot%202025-11-24%20123335.png)
![](images/Screenshot%202025-11-24%20123537.png)


**Adding users to their groups**

![](images/Screenshot%202025-11-24%20123801.png)
![](images/Screenshot%202025-11-24%20130623.png)
![](images/Screenshot%202025-11-24%20130635.png)
![](images/Screenshot%202025-11-24%20130705.png)
![](images/Screenshot%202025-11-24%20130715.png)


**Creating an Admin level user**

![](images/Screenshot%202025-11-24%20131054.png)
![](images/Screenshot%202025-11-24%20131129.png)
![](images/Screenshot%202025-11-24%20131151.png)
![](images/Screenshot%202025-11-24%20131200.png)
![](images/Screenshot%202025-11-24%20131228.png)
![](images/Screenshot%202025-11-24%20131256.png)
![](images/Screenshot%202025-11-24%20131329.png)
![](images/Screenshot%202025-11-24%20131340.png)

---

**Group Policies**

1. A baseline policy for all computers (password policies, firewall, Windows Update)
2. A user policy for standard users (desktop wallpaper, restrictions, drive mapping)
3. A server management policy (administrative tools unlocked for IT staff)

**Creating a Baseline GPO for All Domain Computers**

![](images/Screenshot%202025-11-24%20132117.png)
![](images/Screenshot%202025-11-24%20132409.png)
![](images/Screenshot%202025-11-24%20132439.png)
![](images/Screenshot%202025-11-24%20132840.png)
![](images/Screenshot%202025-11-24%20132939.png)
![](images/Screenshot%202025-11-24%20133106.png)
![](images/Screenshot%202025-11-24%20133248.png)
![](images/Screenshot%202025-11-24%20133346.png)
![](images/Screenshot%202025-11-24%20133438.png)
![](images/Screenshot%202025-11-24%20132535.png)
![](images/Screenshot%202025-11-24%20133832.png)


**Creating a GPO for Standard Users**

I first created the GPO by going to Start → Group Policy Management (gpmc.msc). Expand Forest → Domains → lab.local → Group Policy Objects. Right-click Group Policy Objects → New. Then I named the GPO "GPO - Standard User Experience"

![](images/Screenshot%202025-11-26%20114703.png)

Then I edited the GPO by first setting a Desktop wallpaper. User Configuration → Policies → Administrative Templates → Desktop → Desktop → Desktop Wallpaper. 

Set: Wallpaper Name: \\lab.local\SYSVOL\lab.local\scripts\wallpaper.jpg 

Wallpaper Style: Fill (or Fit)

Apply → OK.

![](images/Screenshot%202025-11-26%20115305.png)


Next I disabled control panel access. User Configuration → Administrative Templates → Control Panel → Prohibit access to Control Panel and Settings

Set to Enabled.

![](images/Screenshot%202025-11-26%20115407.png)


After that I hid tools by going to User Configuration → Administrative Templates → Start Menu and Taskbar.

I first enabled Remove Run menu from Start Menu
![](images/Screenshot%202025-11-26%20115651.png)

I then enabled prevent access to the command prompt
![](images/Screenshot%202025-11-26%20120338.png)

I then removed task manager
![](images/Screenshot%202025-11-26%20120649.png)

After this I set up drive mapping by going to User Configuration → Preferences → Windows Settings → Drive Maps.

Right-click → New → Mapped Drive

Set:

Action: Update

Location: \\lab-dc\Shared (you’ll create this folder in step 7)

Drive Letter: H:

Label: Shared Drive (optional)

Apply → OK.

![](images/Screenshot%202025-11-26%20120828.png)
![](images/Screenshot%202025-11-26%20120914.png)
![](images/Screenshot%202025-11-26%20120955.png)


Finally I linked the GPO to the Users OU.

![](images/Screenshot%202025-11-26%20121117.png)

**Creating a GPO for IT Admin Users**

Back in Group Policy Management:

Right-click Group Policy Objects → New

Then I named it "GPO - IT Admin Tools"

![](images/Screenshot%202025-11-26%20123135.png)

Next I edited the GPO to first enable admin tools by going to User Configuration → Administrative Templates → Control Panel → Control Panel: Prohibit access to Control Panel

Set to Disabled

![](images/Screenshot%202025-11-26%20123410.png)

I then enabled command prompt by navigating to User Configuration → Administrative Templates → System.

Prevent Access to Command Prompt → Disabled
Prevent access to registry editing tools → Disabled

![](images/Screenshot%202025-11-26%20123528.png)
![](images/Screenshot%202025-11-26%20123547.png)

Next I enabled PowerShell by going to User Configuration → Administrative Templates → Windows Components → Windows PowerShell.

Turn on Script Execution → Enabled
Allow all scripts 

![](images/Screenshot%202025-11-26%20123831.png)

Next I allowed Task Manager by going to User Configuration → Administrative Templates → System → Ctrl+Alt+Del Options.

Remove Task Manager → Disabled

![](images/Screenshot%202025-11-26%20123952.png)

Finally, I linked IT Admin GPO 

![](images/Screenshot%202025-11-26%20124124.png)
