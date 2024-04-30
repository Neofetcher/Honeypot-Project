
# Cloud Honeypot Deplyoment 

## What is a Honeypot

A honeypot is a security mechanism designed to detect, deflect, or study attempts at unauthorized use of information systems. Essentially, it's a decoy system or network that appears to be part of a legitimate network but is actually isolated and closely monitored.

## Objective

This project aims to create a simulated environment designed to attract and deceive potential attackers, thereby capturing their malicious activities for analysis and mitigation. The primary objective is to enhance understanding of cyber threats and improve defensive strategies by studying the tactics, techniques, and procedures (TTPs) employed by adversaries. Key goals include identifying common attack vectors, assessing the effectiveness of existing security measures, and gathering threat intelligence to bolster proactive defense mechanisms. Through the deployment of honeypots, researchers and security professionals seek to uncover new attack trends, analyze attacker behavior, and develop countermeasures to mitigate risks to organizational assets. By simulating vulnerable systems and services, the project aims to divert and contain malicious activity away from critical infrastructure while providing valuable insights into the evolving threat landscape. Ultimately, the honeypot project serves as a proactive tool for enhancing cybersecurity posture, facilitating incident response preparedness, and fostering continuous improvement in defensive capabilities.

## Skills Learned

- Network Monitoring: You learn how to monitor network traffic effectively to identify suspicious activities and potential threats.
- Threat Intelligence: Analyzing honeypot data can enhance your ability to identify common attack patterns, tactics, and techniques used by cyber adversaries.
- Forensics: Honeypot projects often involve forensic analysis of captured data to understand the nature and scope of security incidents. This includes examining log files, packet captures, and other artifacts.
- Security Tool Familiarity: Working with honeypots exposes you to various security tools and technologies used in cybersecurity, such as intrusion detection systems (IDS), network monitoring tools, and SIEM (Security Information and Event Management) platforms.

## Tools Used

- T-Pot - The All In One Multi Honeypot Platform : https://github.com/telekom-security/tpotce
- Amazon web Services : https://aws.amazon.com/
- Kali Linux : https://www.kali.org/

## Steps

###  SETTING UP AWS

 - Launch a instance using aws or any other cloud provider.

 - System Requirements for the Honeypot : https://github.com/telekom-security/tpotce?tab=readme-ov-file#system-requirements 
 
 - Choose a amazon machine image (AMI) preferably Debian 12 with support by supported images

    ![image](https://github.com/Neofetcher/Honeypot-Project/assets/166114015/3fe5cd89-c2b8-4b21-ab7b-154d887ae67c)

 - Choose your instance type t3.xlarge with 4vcpu's and 16gb of ram

    ![image](https://github.com/Neofetcher/Honeypot-Project/assets/166114015/85473fdc-0f00-4517-872a-4c14dc2aef76)

 - Configure your storage atleast 128gb

    ![image](https://github.com/Neofetcher/Honeypot-Project/assets/166114015/b0ce36ac-4d9e-4bb8-8556-459cc464833c)
 
 - Create a Key for your instance and download it

 - Lanch your instance and wait for it to intialize

    ![instance](https://github.com/Neofetcher/Honeypot-Project/assets/166114015/78189971-80b7-465f-a91c-e01526f98d09)

### CONNECTING AND SETTING UP THE INSTANCE 

 - Open Terminal and use the command chmod 400 (your-key-name).pem

   ![chmod ](https://github.com/Neofetcher/Honeypot-Project/assets/166114015/79060e29-ba78-425c-ba64-1ea5c2fd860a)

 - SSH into your instance

   ![Screenshot 2024-04-30 111016](https://github.com/Neofetcher/Honeypot-Project/assets/166114015/98fa4eef-3bcf-47aa-acd3-d3277837e26a)

 - After connecting update your instance using sudo apt update & sudo apt upgrade commands
 - Install git

    ![Screenshot 2024-04-30 105804](https://github.com/Neofetcher/Honeypot-Project/assets/166114015/e6703181-a7c3-43aa-b841-e89d4a129481)

### INSTALLING THE HONEYPOT USING TPOTCE

 - Clone the tpotce repository using the command - git clone https://github.com/telekom-security/tpotce.git

   ![Screenshot 2024-04-30 105906](https://github.com/Neofetcher/Honeypot-Project/assets/166114015/33e1410e-2294-4ec3-8ad6-e34c5d2b19dc)
 
 -  cd into the tpotce directory command: cd tpotce/ after that use the command ls

    ![Screenshot 2024-04-30 105938](https://github.com/Neofetcher/Honeypot-Project/assets/166114015/d09ff00c-22f6-43cd-a018-c41e44a0431a)

 - install the honeypot : ./install.sh --type=user
 
   ![Screenshot 2024-04-30 110319](https://github.com/Neofetcher/Honeypot-Project/assets/166114015/9aa59764-8543-418b-bbdc-9150d2d12a20)
 
 - Choose your tpot type Hive or Sensor

   ![Screenshot 2024-04-30 110451](https://github.com/Neofetcher/Honeypot-Project/assets/166114015/26b1ee20-5df8-48f8-a0a5-cb7dbfa3697c)

![image](https://github.com/Neofetcher/Honeypot-Project/assets/166114015/766bef4b-e550-4e84-b665-4d285be437bd)

 - Enter a username and password for the web-interface

   ![Screenshot 2024-04-30 110534](https://github.com/Neofetcher/Honeypot-Project/assets/166114015/32997dad-acb3-4223-ba00-fead6890c841)

 - After the installation is completed reboot your instance

   ![Screenshot 2024-04-30 110757](https://github.com/Neofetcher/Honeypot-Project/assets/166114015/8308ad18-a66e-4a04-94f3-b14dda0889bb)

### CHANGE THE SECURITY RULES IN YOUR INSTANCE 

 - Go to security tab > Inbound rules > Edit inbound rules

   ![Screenshot 2024-04-30 110831](https://github.com/Neofetcher/Honeypot-Project/assets/166114015/8d10ecb0-cb3c-4f59-af5e-581c5bf53ec7)

 - Add Three new rules these new rules will allow us to connect to the instance

   ![Screenshot 2024-04-30 110937](https://github.com/Neofetcher/Honeypot-Project/assets/166114015/689faff7-23bd-4463-a8bf-43b0889f90d2)

 - Save your changes

### ACCESSING THE HONEYPOTS AND LOGS

 - Now you can connect to your instance and the web interface using these commands:

   ![Screenshot 2024-04-30 111016](https://github.com/Neofetcher/Honeypot-Project/assets/166114015/e812b61f-4bd8-4906-86b6-ecb6ddaa333b)
 
 - The command to connect to the web interface : https://<your.ip>:64297

 - Enter your Username and Password to connect

   ![sign in](https://github.com/Neofetcher/Honeypot-Project/assets/166114015/c5a13571-b9a2-4e98-8997-99efe19e814b)

 
 - T-POT Landing Page :

   ![top](https://github.com/Neofetcher/Honeypot-Project/assets/166114015/42162e25-a9be-4a76-9b55-b28bde7e0ed0)

### KIBANA DASHBOARD 

   ![kibana_a](https://github.com/Neofetcher/Honeypot-Project/assets/166114015/ed81be5d-7f66-4b61-a69c-1f2a90cf64fa)

### ATTACK MAP DASHBOARD 

  ![attackmap](https://github.com/Neofetcher/Honeypot-Project/assets/166114015/9d8888c9-a3ca-4388-9a0e-ec82154d78ad)

### CYBERCHEF

  ![cyberchef](https://github.com/Neofetcher/Honeypot-Project/assets/166114015/1063b679-cae8-42a1-beaf-b0d931a31b20)

### ELASTICVUE

  ![elasticvue](https://github.com/Neofetcher/Honeypot-Project/assets/166114015/77d127fe-77d1-400a-b136-e648293b287a)


## DISCLAMER 

This project is intended for educational purposes only. Use responsibly and only with proper authorization on systems you own or have explicit permission to monitor.


   

