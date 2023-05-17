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

<br> Turn off all these: <br>
![Screenshot 2023-05-17 160817](https://github.com/Kairos-T/TrojanAttack-Walkthrough/assets/80029462/f0a10749-06a3-4f04-910e-dafc466a6f01)

![Screenshot 2023-05-17 160924](https://github.com/Kairos-T/TrojanAttack-Walkthrough/assets/80029462/51f8521e-0e4a-46c2-9f1c-c01a177678db)

![Screenshot 2023-05-17 160938](https://github.com/Kairos-T/TrojanAttack-Walkthrough/assets/80029462/4c14cf85-3643-4461-acdd-78c000b8edcf)
<br> Turn off all three networks' firewall. <br>
![Screenshot 2023-05-17 161023](https://github.com/Kairos-T/TrojanAttack-Walkthrough/assets/80029462/a1c79c75-dc62-4dd3-b76c-65d1b9aaa541)
![Screenshot 2023-05-17 161011](https://github.com/Kairos-T/TrojanAttack-Walkthrough/assets/80029462/e60d21de-da63-44d2-83be-be8350172e74)
<br>

3. Download Prorat [zip file](https://prorat.software.informer.com/1.9/) on attacker machine.
4. Create a new folder in C:\ drive and move the zip file.
5. In Windows Security > Virus & Threat Protection, click manage settings > Exclusions > Add or remove exlclusions > Folder and select the folder path. 
6. Extract the files from the zip file, and run ProRat software as administrator. 
7. Click the "Create" button at the bottom annd choose "Create ProRAT server"
8. Click on "Bind with File", and select a file to bind (I used an image file of, you guessed it, a CAT :D )
9. Click on server icon and choose a non-suspicious file icon.
<br> ![Screenshot 2023-05-17 161820](https://github.com/Kairos-T/TrojanAttack-Walkthrough/assets/80029462/919b4137-496b-4e13-a214-b007476fdbbc)
<br> (Image credits to NP :P )
10. Click "Create Server", and use 7-zip to: Add to Archive > Select "zip" as archive format and set a password for encryption
11. Upload file to [file sharing services](www.file.io/) and open the link in your victim machine.
12. Extract the contents of the zip file and run as administrator.
13. On victim's machine, use command
``` ipconfig ``` 
in cmd to check the IPv4 address and copy it. 
![image](https://github.com/Kairos-T/TrojanAttack-Walkthrough/assets/80029462/6ed2d667-993b-4b45-805c-205cc0ecda2e)

14. On attacker's machine:
<br> ![Screenshot 2023-05-17 162252](https://github.com/Kairos-T/TrojanAttack-Walkthrough/assets/80029462/0a13f859-0efe-4abb-aee0-42703df9c2f7) <br>
paste the IP address into Ip field and click connect.  (Image credits to NP :P )
15. On the left panel, there are different functions like "Funny Stuff" to control the victim machine, like hiding desktop icons.
<br> ![image](https://github.com/Kairos-T/TrojanAttack-Walkthrough/assets/80029462/e0cd8e7a-4014-4870-9d57-b090ac7f38d9) <br>
17. There is also a keylogger (keystroke logger) function that can record the interactions in the Victim machine  like what is typed on the victim's machine.
