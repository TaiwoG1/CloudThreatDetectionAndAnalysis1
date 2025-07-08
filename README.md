<h1>Cloud Threat Intelligence, Detection and Analysis (Azure & Microsoft Sentinel)</h1>


<h2>Description</h2>
This project involved the end-to-end development and deployment of a cloud-based threat intelligence platform utilizing a deliberately exposed Azure Virtual Machine as a honeypot. The primary objective was to attract, monitor, and analyze live cyber attacks, ingesting the resulting security logs into a Microsoft Sentinel SIEM (Security Information and Event Management) tool. This setup provided invaluable hands-on experience in cloud infrastructure deployment, sophisticated log management, real-time threat analysis using Kusto Query Language (KQL), and advanced data visualization for proactive security posture enhancement.
<br />
<br />
Project Objectives:

- <b2> Establish a Controlled Honeypot: Deploy an Azure Virtual Machine configured to be visible and attractive to network-based attacks. </b2>
- <b2> Implement Robust Log Ingestion: Configure seamless collection of security events from the honeypot into a centralized log repository. </b2>
- <b2> Integrate Cloud-Native SIEM: Connect log data to Microsoft Sentinel for advanced security analytics. </b2>
- <b2> Perform Real-time Threat Monitoring: Utilize KQL to analyze, filter, and prioritize live cyber attack data. </b2>
- <b2> Visualize Attack Patterns: Map attack origins and frequency to gain actionable threat intelligence. </b2>
<br />


<h2>Technical Architecture & Honeypot Deployment</h2>
The project commenced with the foundational deployment of resources within an Azure subscription. This involved creating a dedicated Resource Group to logically organize all components, followed by the establishment of a Virtual Network to define the isolated network boundary. A Windows Virtual Machine (VM) was then provisioned within this network, designed with a specific VM account for administrative access. To ensure the VM's quick discovery and visibility as a honeypot, its private and public network firewalls (including the domain profile) were strategically disabled, creating a vulnerable target for inbound network traffic. Connectivity was verified through successful pings from a local host machine. 

A Log repository created within Azure (Log Analytics Workspace) was used to retrieve the logs from the Virtual Machine, Microsoft Sentinel (SIEM) was then used to analyze and create the attack map, consisting of an IP mapped to a location, which was then plotted on the map.

<p align="center">
Azure VM Creation Process (VM details page with name, OS, public IP visible): <br/>
<img src="https:" height="80%" width="80%" alt="Azure VM Creation Process"/>
<br />
</p>
<br />


<h2>Log Ingestion & Microsoft Sentinel Integration</h2>
To transform raw security events into actionable intelligence, a comprehensive logging and SIEM integration strategy was implemented:
<br />
<br />

- <b2> Log Analytics Workspace (Log Repository): A dedicated Log Analytics Workspace was established to serve as the centralized repository for all security event data collected from the honeypot VM. </b2>
  <p align="center">
  Azure VM Creation Process (VM details page with name, OS, public IP visible): <br/>
  <img src="https:" height="80%" width="80%" alt="Azure VM Creation Process"/>
  <br />
  </p>
  <br />
- <b2> SIEM Linkage: The Log Analytics Workspace was seamlessly linked to Microsoft Sentinel, providing the SIEM tool with direct access to the ingested logs for security analytics and threat hunting. </b2>
  <p align="center">
  Linking Log Analytics Workspace to Microsoft Sentinel (Sentinel "Workspaces" blade showing the connected LA Workspace): <br/>
  <img src="https:" height="80%" width="80%" alt="Linking Log Analytics Workspace to Microsoft Sentinel"/>
  <br />
  </p>
  <br />
- <b2> Windows Security Event Collection: The Windows VM was configured to forward essential security events, ensuring comprehensive logging of activities within the honeypot.   </b2>
  <p align="center">
  Windows Security Event Collection: <br/>
  <img src="https:" height="80%" width="80%" alt="Windows Security Event Collection"/>
  <br />
  </p>
  <br />
- <b2> Data Collection Rule (DCR-Windows): A custom Data Collection Rule was meticulously created and applied to the VM. This rule dictated precisely which logs were to be forwarded from the Windows VM to the Log Analytics Workspace, enabling efficient and targeted data ingestion into Sentinel. </b2>
  <p align="center">
  Data Collection Rule (DCR-Windows) Configuration (showing the rule's settings for event collection): <br/>
  <img src="https:" height="80%" width="80%" alt="Data Collection Rule (DCR-Windows) Configuration"/>
  <br />
  </p>
  <br />
<br />



<h2>Threat Monitoring, Analysis & Visualization</h2>
With logs flowing into Sentinel, the project advanced to the crucial phases of real-time monitoring and in-depth analysis:
<br />
<br />

- <b2> Kusto Query Language (KQL) Analytics: Advanced KQL queries were developed and utilized within Microsoft Sentinel to filter, analyze, and prioritize incoming security events, enabling the identification of attack attempts, reconnaissance activities, and anomalous behaviors. </b2>
  <p align="center">
  Microsoft Sentinel Dashboard/KQL Query Window (query for failed RDP attempts or top attacking IPs): <br/>
  <img src="https:" height="80%" width="80%" alt="Microsoft Sentinel Dashboard/KQL Query Window"/>
  <br />
  </p>
  <br />
- <b2> IP Geolocation & Threat Mapping: Collected IP addresses from attack logs were enriched using an external CSV file to map them to corresponding longitude and latitude coordinates. This geolocation data was then used to visually represent the global origins of attacks.
  </b2>
  <p align="center">
  Geo-mapped Attack Frequency (world map visualization in Sentinel Workbooks showing attack origins/intensity): <br/>
  <img src="https:" height="80%" width="80%" alt="Geo-mapped Attack Frequency"/>
  <br />
  </p>
  <br />
- <b2> Live Attack Data Visualization: Microsoft Sentinel's powerful visualization capabilities, including Workbooks, were employed to create dynamic dashboards. These dashboards provided real-time insights into attack frequency, attack types, and geographical distribution, facilitating rapid understanding and response to observed threats.   </b2>
  <p align="center">
  Sentinel Workbooks/Attack Logs at Specific Time Ranges (chart showing attack volume over time or a list of recent attacks): <br/>
  <img src="https:" height="80%" width="80%" alt="Sentinel Workbooks/Attack Logs at Specific Time Ranges"/>
  <br />
  </p>
  <br />

<br />



<h2>Key Learnings & Outcomes</h2>
This project provided invaluable practical experience in:
<br />
<br />

- <b2> Deploying and securing resources in a major cloud platform (Azure). </b2>
- <b2> Implementing log management solutions for security monitoring. </b2>
- <b2> Leveraging a leading SIEM tool (Microsoft Sentinel) for threat detection, analysis, and prioritization. </b2>
- <b2> Utilizing KQL for advanced security analytics and data correlation. </b2>
- <b2> Transforming raw security logs into actionable threat intelligence through visualization and geolocation. </b2>
- <b2> This initiative cultivated a strong foundation in proactive cybersecurity defense and incident response methodologies within a cloud environment. </b2>

<br />






