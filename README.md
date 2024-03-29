<h1>Active Directory in VirtualBox</h1>

Prerequisite
--
- Would recommend using a device with at least 16GB of RAM, anything below can be very slow.

Environments and Technologies Used
--
- Oracle VirtualBox

Operating Systems Used
-- 
- Windows 10
- Windows Server 2019

1. Check that your machine has virtualisation enabled

<img src="https://i.imgur.com/MLrk2ra.png" height="50%" width="50%" alt="Performance screen"/>

2. Download and install VirtualBox
3. Search 'Windows server 2019 evaluation' and download the ISO
   
4. Create the DC (Domain controller) in VirtualBox
   - Select the ISO Image you downloaded in the previous step.
   - Check 'Skip Unattended Installation'
   - Choose 4GB RAM and 2 Processors

5. In DC settings
   - System --> Uncheck Floppy
   - Network --> Attached to: Bridge Adapter
  
6. Start DC

7. Install Windows Server 2019
   - Select 'Datacenter Evaluation (Desktop Experience)'
   - Custom: Install Windows only
  
8. Add a password for the local admin account

**Note:** Input --> Keyboard to Ctrl + Alt + Delete

9. Change the name of the machine to DC

10. Download Windows 10
    - Search 'Windows 10 evaluation download'
    - Select 'Download the ISO - Enterprise'

11. Create a Windows 10 machine in VirtualBox
    - Select the Windows 10 ISO you have just downloaded
    - Check 'Skip Unattended Installation'
    - I have set 4GB RAM and 2 Processors
<img src="https://i.imgur.com/dwqhxQu.png" height="50%" width="50%" alt="Performance screen"/>

12. Change the settings of the Windows 10 Machine
    - System --> Uncheck Floppy
    - Network --> Change from NAT to Bridged Adapter
   
13. Start the Windows 10 Machine and finish the installation

14. Once you have reached the screen in the image below, power off and clone the machine
    
    <img src="https://i.imgur.com/vD5HX2v.png" height="50%" width="50%" alt="Performance screen"/>

15. Start a Windows 10 machine
    - Select 'Join Domain instead'
    - Enter a name and password
    - Change the name of the machine
   
16. Add Active Directory to the Domain controller
    - Add roles and features --> Active Directory Domain Services
    - Promote this server to a domain controller
    - Add a new forest
    - Uncheck Create DNS delegation
   
17. In Active Directory create a user with admin privileges
    - Active Directory Users and Computers
    - Right click --> New --> User
    - Right click the user --> Properties --> Member of --> Add --> Type Domain admins --> Check Names --> Apply --> OK
   
18. Add a computer to the domain
    - System --> Rename this PC (advanced) --> Change --> Domain --> Type domain name --> If get an error change the DNS server to the DC's IP address
    - Enter the username and password of an account with this access
    - Computer will restart
    - Screenshot below shows that Client-1 has been added to the domain

      <img src="https://i.imgur.com/L4LTcP0.png" height="50%" width="50%" alt="Active Directory showing computers in the domain"/>
