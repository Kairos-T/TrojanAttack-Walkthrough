## Background
This is a walkthrough of the deployment of a trojan using ProRAT on an unpatched Windows 10 virtual machine (VM) through a Windows 11 VM. ProRAT is a remote administration tool (RAT) that is a common tool employed by hackers to gain unauthorised access to the system. It is a Windows-based backdoor Trojan that is used to control the victim's machine over a network.

## Tools
1. Virtualisation Software: VM Ware Pro
3. Windows 11 VM (Attacker's Platform) installed with ProRAT (installation in [steps](https://github.com/Kairos-T/TrojanAttack-Walkthrough/edit/main/Trojan%20Attack%20Walkthrough.md#steps)) and 7zip
4. Windows 10 VM (Victim's Platform): Unpatched Windows 10 virtual machne that simulates a vulnerable system
5. Network Configuration: Set up virtual networking environment to establish communication between attacker and victim's VM through using NAT.

### Steps: 
1. Ensure that both VMs are using NAT as Network Adapter. 
2. Disable Firewall & Network Protection and Virus & Threat Protection Settings for both VMs from Windows Security. <br>  
![image](https://github.com/Kairos-T/TrojanAttack-Walkthrough/assets/80029462/a494786e-8ccd-4e73-ae5a-33f32bd75529)
![image](https://github.com/Kairos-T/TrojanAttack-Walkthrough/assets/80029462/831c0b18-3630-4cd9-a55c-3c150d4537ac)
<br> Turn off all these: <br>
![image](https://github.com/Kairos-T/TrojanAttack-Walkthrough/assets/80029462/9a2f1d78-e29d-47b8-a9c1-a7229d3a672e)
<br> Turn off all three networks' firewall. <br>

![image](https://github.com/Kairos-T/TrojanAttack-Walkthrough/assets/80029462/8d9a386f-e2b6-48b5-9b4e-97fc842e4729)
![image](https://github.com/Kairos-T/TrojanAttack-Walkthrough/assets/80029462/7824757d-4d29-494d-bbc9-47ca5488e67d)
<br>

3. Download Prorat [zip file](https://prorat.software.informer.com/1.9/) on attacker machine.
4. Create a new folder in C:\ drive and move the zip file.
5. In Windows Security > Virus & Threat Protection, click manage settings > Exclusions > Add or remove exlclusions > Folder and select the folder path. 
6. Extract the files from the zip file, and run ProRat software as administrator. 
7. Click the "Create" button at the bottom annd choose "Create ProRAT server"
8. Click on "Bind with File", and select a file to bind (I used an image file of, you guessed it, a CAT :D )
9. Click on server icon and choose a non-suspicious file icon.
<br> ![image](https://github.com/Kairos-T/TrojanAttack-Walkthrough/assets/80029462/08ab0117-9a68-4573-89e8-5969e7028d81)
<br> (Image credits to NP :P )
10. Click "Create Server", and use 7-zip to: Add to Archive > Select "zip" as archive format and set a password for encryption
11. Upload file to [file sharing services](www.file.io/) and open the link in your victim machine.
12. Extract the contents of the zip file and run as administrator.
13. On victim's machine, use command
``` ipconfig ``` 
in cmd to check the IPv4 address and copy it. 
14. On attacker's machine:
<br> ![image](https://github.com/Kairos-T/TrojanAttack-Walkthrough/assets/80029462/f6abaf37-eb97-43ae-a3c2-480ae1334214) <br> (Image credits to NP :P )
paste the IP address into Ip field and click connect. 
