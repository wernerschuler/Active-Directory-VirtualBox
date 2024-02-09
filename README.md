# Active-Directory-VirtualBox

Prerequisits
--
- Would reccommend using a device with at least 16GB of RAM, anything below can be very slow.

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
