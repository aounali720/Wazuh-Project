
# Wazuh-Agents

## Objective
[Brief Objective - Remove this afterwards]
The primary objective of installing the Wazuh agent on both Windows and Ubuntu virtual machines and configuring it to connect with the Wazuh Manager is to enable centralized security monitoring, threat detection, and incident response across multiple platforms. The Wazuh agent acts as a local component on the machines that gathers security event data, system logs, and other relevant information, which it then sends to the Wazuh Manager for analysis and correlation.
### Skills Learned
[Bullet Points - Remove this afterwards]
- System Administration and Configuration:

  - Gaining hands-on experience with both Windows and Ubuntu operating systems by installing software, configuring system services, and managing dependencies.

- Learning how to install software packages using:
  - Windows: Installing through installers (MSI/EXE) or using PowerShell.
  - Ubuntu: Using package managers like apt to install the Wazuh agent.
- Command-Line Proficiency:

   - Linux/Ubuntu: Improving proficiency in terminal commands for navigating the file system, installing software, and managing services.
   - Windows: Using PowerShell and Command Prompt to configure network settings and install the Wazuh agent.
- Network Configuration:

   - Understanding how to configure virtual machines to communicate with each other, particularly setting up network interfaces to enable the Wazuh agent to connect to the Wazuh Manager.
  - Learning about ports, protocols, and firewall settings required for secure communication between the agent and the manager.
- Agent Configuration:

   -  Editing configuration files on both Windows and Linux systems (e.g., ossec.conf) to connect the Wazuh agent to the Wazuh Manager.
   -  Understanding configuration parameters, such as manager IP address, agent ID, and encryption options.
- Service Management:

  -  Starting, stopping, and checking the status of the Wazuh agent service on both operating systems:
  -  Ubuntu: Using systemctl to manage services.
  -  Windows: Using services.msc or PowerShell for service control.
- Log Management and Analysis:

   - Learning where logs are stored on both systems and how to analyze logs to ensure that the Wazuh agent is functioning properly and communicating with the manager.
   - Troubleshooting any connectivity or configuration issues by reviewing error logs and status reports.
- Security Monitoring Setup:

  - Understanding the Wazuh security architecture and learning how to set up agents for proactive monitoring, file integrity checking, log analysis, and event correlation across diverse environments.
- Cross-Platform Troubleshooting:

  - Identifying and resolving issues in different operating environments (Windows vs. Ubuntu), including troubleshooting connectivity, configuration, and service errors.
 - Automation and Scripting:

   - Writing or using scripts for automating the installation or configuration process, particularly in Ubuntu using Bash scripting or PowerShell scripting on Windows.
Basic Cybersecurity Knowledge:

   - Gaining a foundational understanding of security monitoring principles, log analysis, and how systems are monitored for security threats like malware, unauthorized access, and system changes.
- Virtualization:

   - Setting up and managing virtual machines on hypervisors like VMware, VirtualBox, or Hyper-V to simulate real-world environments.


### Tools Used
- Wazuh Agent:

  - The software agent that collects security-related data (logs, file changes, network activity) from the host system (Windows/Ubuntu) and forwards it to the Wazuh Manager for analysis.
Wazuh Manager:

  - Central server where data from agents is processed, correlated, and visualized. It is used to manage agents, configure security rules, and analyze security events.
Virtualization Tools:

- To create virtual environments where Wazuh agents are installed:
  - VMware Workstation / VMware Fusion: For creating and managing Windows and Ubuntu virtual machines.
VirtualBox: An alternative open-source virtualization tool for creating virtual machines.

- Package Managers:

  - APT (Advanced Package Tool): Used on Ubuntu to install and manage software packages, including the Wazuh agent.


- Terminal/Command-Line Interface (CLI):

  - Linux/Ubuntu Terminal: For executing system commands, installing the Wazuh agent, managing services, and editing configuration files.
  - Command Prompt or Windows Terminal: For running basic commands and scripts in the Windows environment.
- Text Editors:
  - Used to edit configuration files for the Wazuh agent, especially the ossec.conf file.
  - Windows: Notepad, Notepad++.
  - Ubuntu: Nano, Vim, or other CLI-based text editors.
- System Monitoring and Management Tools:
  - Systemctl (Ubuntu/Linux): Command-line utility for managing system services (starting, stopping, checking status of the Wazuh agent).
  - Example: sudo systemctl status wazuh-agent
  - Windows Services: Used to manage the Wazuh agent service on Windows.
- Accessed through services.msc.Wazuh Agent:
  - The software agent that collects security-related data (logs, file changes, network activity) from the host system (Windows/Ubuntu) and forwards it to the Wazuh Manager for analysis.
- Wazuh Manager:
  - Central server where data from agents is processed, correlated, and visualized. It is used to manage agents, configure security rules, and analyze security events.
- Virtualization Tools:

  - To create virtual environments where Wazuh agents are installed:
  - VMware Workstation / VMware Fusion: For creating and managing Windows and Ubuntu virtual machines.

  

## Step-1
To install the wazuh agent on our endpoint(windows-machine)<br>
We go to the wazuh official website to download the package (exe-file)<br>
It is recommended to install the exefile the gui version for easier installation.<br>
After the download has completed.<br>
Run the wazuh-agent.exe file on the endpoint<br>
*Ref 1: Wazuh-agent-install*
![wazuh agent on widows intsall](https://github.com/user-attachments/assets/2815ae3d-0277-46b6-95da-19871f266a43)
After the installation has completed <br>
Check the " Run wazuh agent configuration interface " and click finish<.br>

## Step-2:
In the interface enter the manager ip that is your wazuh ip meaning (cloud ip for connection) and save.<br>
*Ref 2: Agent-interface*
![wazuh agent interface](https://github.com/user-attachments/assets/b28c3b16-e3c2-40f9-99a8-48dbdfe2bad6)
After that go in the config view in the view tab <br>
Here we are going to configure the  config file to enable osquery for osquery integration.<br>
*Ref 3: Osquery-config*
![agent windows os query on](https://github.com/user-attachments/assets/55f1359c-a1b8-496e-acec-ab272b09c5dc)
And in the view tab we can view the logs of the log file that are going to be monitored.<br>
*Ref 4: Agent-logs*

![wazuh agent logs view](https://github.com/user-attachments/assets/f8a13c33-2207-4bea-9aad-58e2604636a2)<br>
After restarting the agent the api key will be generated <br>
## Step-3:
Now we check if our agent has connected with the wazuh server<br>
Open the wazuh dashboard on the browser and check the agents.<br>
*Ref 5: wazuh agent status*

![wazuh-dashboard-agent-active](https://github.com/user-attachments/assets/905d6421-827b-4627-8294-1500bc215ee0)
On the Dashboard in the top left corner we can see the agent summary and see the active agent.<br>
*Ref 6: agent status*

![Screenshot 2024-09-28 014152](https://github.com/user-attachments/assets/34b976e9-4609-44ec-82cd-04ebc6c6ab73)<br>
Here we can see the windows-agent has connected and sending logs.<br>

### Ubuntu-Agent
## Step-1
Now we are going to set up on a linux-virtual-Machine <br>
open the terminal.<br>
Using the following command we can connect the wazuh agent key repo on the machine.<br>
``
apt-get install gnupg apt-transport-https
curl -s https://packages.wazuh.com/key/GPG-KEY-WAZUH | apt-key add -
echo "deb https://packages.wazuh.com/4.x/apt/ stable main" | tee -a /etc/apt/sources.list.d/wazuh.list 
``<br>

For debian-7,8 and 14 for other check wazuh agent Documentation.<br>
*Ref 7: agent ubuntu*
![add-repo-ubuntu-cloud](https://github.com/user-attachments/assets/81c16bd6-3109-43d7-acdb-61aaaf29aaed)

The necessary dependencies will be downloaded.<br>
## Step-2
To connect to Wazuh manager and download wazuh agent use the following command  .<br>
Change the ip to the wazuh cloud ip <br>
``WAZUH_MANAGER="10.0.0.2" apt-get install wazuh-agent``<br>

## Step-3
After the installation is completed .<br>
Using the following command we can configure our machine to start wazuh agent on startup.<br>
``systemctl daemon-reload
systemctl enable wazuh-agent
systemctl start wazuh-agent
``<br>

*Ref 8: system ctl command*
![using system ctl for agent](https://github.com/user-attachments/assets/5af2a73d-902a-47f2-a773-149c3902e1b2)
<br>

## Step-4
After the installation has completed and the wazuh agent has started.<br>
We can now go to the wazuh dashboard to check the agent status.<br>
*Ref 9: agent summary*
![dashboard wazuh agents ](https://github.com/user-attachments/assets/8274f0da-fec2-4243-af1c-fa8f5b68a6e5)
Here we can see the agent(endpoint) has connected to the wazuh server .<br>



*Ref 1: Network Diagram*




