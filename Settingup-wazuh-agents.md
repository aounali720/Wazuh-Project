
# PROJECTNAME

## Objective
[Brief Objective - Remove this afterwards]

The Detection Lab project aimed to establish a controlled environment for simulating and detecting cyber attacks. The primary focus was to ingest and analyze logs within a Security Information and Event Management (SIEM) system, generating test telemetry to mimic real-world attack scenarios. This hands-on experience was designed to deepen understanding of network security, attack patterns, and defensive strategies.

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

## Step-1:
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
After restarting the agent the api key will be generated <br>




Example below.

*Ref 1: Network Diagram*



