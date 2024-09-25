# Wazuh-Project

## Objective
The objective of this project is to successfully install Wazuh on a Cloud Ubuntu server and configure a Wazuh agent on a designated endpoint. This will enhance security monitoring by providing real-time visibility into system and application logs, threat detection, and compliance management. The project aims to establish a centralized security management system that effectively detects and responds to potential security threats, while also allowing for scalability and flexibility in managing cloud resources. By the end of the project, the Wazuh server should be fully operational, with properly configured agents reporting data back to the server, facilitating a robust security posture.
### Skills Learned
[Bullet Points - Remove this afterwards]

- Advanced understanding of SIEM concepts and practical application.
- Proficiency in analyzing and interpreting network logs.
- Ability to generate and recognize attack signatures and patterns.
- Enhanced knowledge of network protocols and security vulnerabilities.
- Development of critical thinking and problem-solving skills in cybersecurity.

### Tools Used
[Bullet Points - Remove this afterwards]

- Security Information and Event Management (SIEM) system for log ingestion and analysis.
- Network analysis tools (such as Wireshark) for capturing and examining network traffic.
- Telemetry generation tools to create realistic network traffic and attack scenarios.

## Step-1
First we are going to login to our cloud instance using ssh<br>
After logining in we can update our ubuntu instance with the comman apt command <br>
Completing the update of the ubuntu instance we are going to directly download and install Wazuh <br>
In this project we are going to use the wazuh easy installation guide see wazuh <a href="https://documentation.wazuh.com/current/quickstart.html">official document</a><br>
Using the following command <br>
``
curl -sO https://packages.wazuh.com/4.9/wazuh-install.sh && sudo bash ./wazuh-install.sh -a 
``
with the command the package will download and install .<br>
*Ref 1: wazuh-Assited-install-ubuntu-cloud*
![wazuh-assist-install-cloud](https://github.com/user-attachments/assets/649eb8f3-d3a1-44bf-aeb5-8a86953a976d)

## Step-2
After the installation has completed <br>
Configuring the firewall to allow tcp trafiic on 5601<br>
Reloading it with the following command:<br>
``sudo ufw allow 5601/tcp
sudo ufw reload
``<br>
*Ref 2: ufw-ubuntu-cloud*<br>
![wazuh-cloud-firewall-allow](https://github.com/user-attachments/assets/2f0200a6-b543-4554-bed6-f84311ab9019)
## Step-3
For the usernames and passwords in wazuh we can use the following command to see the credentials<br>
`` tar -O -xvf wazuh-install-files.tar wazuh-install-files/wazuh-passwords.txt
wazuh-install-files/wazuh-passwords.txt``
<br>
After that we can now go to the web-browser and use the synatax to go to the dashboard of wazuh<br>
``https://<ip-address-of-cloud-instance>:443``<br>
Login with the web-dashboard credential<br>
*Ref 3: Login-dashboard*

![wazuh dashboard](https://github.com/user-attachments/assets/755d2afb-1799-4446-a03b-c73b9775c31d)

#Conclusion:
With this we have successfully installed wazuh All-In-One on the ubuntu cloud instance 


