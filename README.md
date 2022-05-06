# Honeypot Server Project

**Time spent:** **5** hours spent in total

**Objective:** 

Honeypot is a computer system, set up as a decoy to lure cyber attackers and detect and study exploit methods. Honeypots look like a real computer system with applications and data, misleading criminals and hackers into thinking it's a legitimate target.Different types of honeypot can be used to identify types of threats and threat actors. My purpose for this project was to capture and study different type of malwares and it's capabilities.
### MHN-Admin Deployment

**Summary:**
I started this project by insalling two Virtual Machines (Ubuntu_18.0) on Google cloud followed by setting up Google SDK on my local machine(linux). After succesfull SSH connection, I created the first vitrual machine named mhn-admin. Since the operating system was a older version of Ubuntu OS, it required couple basic commands such as ```sudo apt update```&```sudo apt install git python-magice -y``` to install necessary libraries in order to get the system ready for the mhn-honeypot server installation.

![mhn-admin](https://user-images.githubusercontent.com/96266650/167210911-dcfcf77d-65f3-4647-9eaa-90d151939fc2.gif)

![FarajiR_ver](https://user-images.githubusercontent.com/96266650/167216387-149f2273-6812-42f6-8d5e-4b33884e4d67.gif)


> I also verified to make sure the admin server is up and running.


### Dionaea Honeypot Deployment 

**Summary:**
After mhn-admin, it was time to setup my first honeypot VM in cloud. [Dionaea Honeypot](https://www.honeynet.org/) is a basic hoenypot system that carries multiple honeypot scripts for different purposes. I chose Ununti/Raspberry Pi-Dionaea script and then I installed it on the second virtual machine. The setup was fairly easy and the entire script got installed by a single ```wget``` command that was provided by the admin server. 


![image](https://user-images.githubusercontent.com/96266650/167217176-1858902e-e795-41a8-b520-83fe3c2f3192.png)
> Repoerted attack was captured from 05/05/2022 8:00 AM (PST) - 05/06/2022 8:00 AM (PST)

### Database Backup

**Summary:** After detecting this many attacks in short period of time I decided to capture and analyze different IP addresses by implmenting a listening session on mhn-admin server and then I was able to extract 5.2 MB of ```.json``` data file from ```mhn-admin server``. I found this method useful for analysing multiple honeypot sensor and payloads. Since I wanted to only study the payloads sent by attackers, I only had one honepot server up and running. 

![Faraji_httop](https://user-images.githubusercontent.com/96266650/167225545-f3f36105-7415-4a4d-96f4-5b28a393589f.gif)
> I used ```htop``` to monitor the admin server to make sure I am the only authenticated user. Just in case!


### Malware Capture and Identification

#### X Malware
![image](https://user-images.githubusercontent.com/96266650/167226029-5664fe34-0ef8-4905-9c9b-8fafcdd29729.png)
> Melicious payloads captured in less than 24hrs

**Summary:** I used [Virustotal](https://www.virustotal.com/gui/home/upload) to check each payload to try and undrestand on what each payload does and how does it effect the operating system. In my case honeypot-1 was cloned as Win32 OS. There fore I recieved many attacks specified to Windows operating system.

The most common payload was [Wannacry](https://www.cisa.gov/uscert/sites/default/files/FactSheets/NCCIC%20ICS_FactSheet_WannaCry_Ransomware_S508C.pdf) ransomware.

MD5 Hash: *a438e69ddcd602a27a400e6b4e626369*

SHA521 Hash: *a531d5e03e8b0c03799c4c6b3387d8cef66cc59f1e98c193b395ad5ecab706458f2d20b9d008b6b7f21ee3429e1c6e52d7cf5c496a37740330beaedc99f68228*

<img src="x-malware.gif">

## Notes

Describe any challenges encountered while doing the assignment.
