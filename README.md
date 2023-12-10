<h1>Azure Sentinel (Live Cyber Attacks)</h1>


<h2>Description</h2>
Within my laboratory environment, I established Azure Sentinel, a Security Information and Event Management (SIEM) system, integrating it with a live virtual machine serving as a honeypot. The objective is to actively monitor and analyze real-time instances of RDP Brute Force attacks originating globally. To enhance my analysis, a tailored PowerShell script will be employed to retrieve geolocation data pertaining to the attackers. This information will be leveraged to plot their geographical locations on the Azure Sentinel Map, enabling comprehensive visual insights into the attack origins.
<br />


<h2>Languages and Utilities Used</h2>

- <b>PowerShell: Extract RDP failed login logs from Windows Event Viewer</b> 
- <b>ipgeolocation.io: IP Address to Geolocation API</b>

<h2>Environments Used </h2>

- <b>Windows 10 VM Remote Desktop Connection</b>

<h2>Program walk-through:</h2>

<p align="center">
I initiated an Azure subscription, establishing a Virtual Machine (VM) within a designated resource group. Additionally, I set up a Log Analytics Workspace to facilitate centralized log management and analysis for enhanced monitoring and insights: <br/>
<img src="https://i.imgur.com/y2ZjBZl.png"/>
<br />
<br />
To integrate the Log Analytics Workspace with the Virtual Machine (VM), I configured the VM to send its logs and telemetry data to the designated workspace. This involved enabling network traffic within the VM firewall to allow outbound communication to the Log Analytics Workspace endpoint. Additionally, I enabled the collection of VM logs specifically within Microsoft Defender for Cloud, ensuring comprehensive monitoring and analysis of security-related events. Subsequently, I established Azure Sentinel and linked it to the VM to leverage its capabilities for advanced threat detection and response. This setup allowed Azure Sentinel to ingest and analyze the security logs and telemetry data from the VM, enabling proactive identification and mitigation of potential security threats.:  <br/>
<img src="https://i.imgur.com/E3P2TqW.png"/>
<br />
<br />
To access the Virtual Machine (VM) from my personal computer, I utilized the Remote Desktop Connection feature. After ensuring that the necessary credentials and permissions were in place, I initiated a remote connection to the VM, establishing a secure desktop session that enabled seamless interaction and management of the VM's environment directly from my private PC: <br/>
<img src="https://i.imgur.com/8HCt55T.png"/>
<br />
<br />
I accessed the Event Viewer logs within the Windows Virtual Machine (VM) to gain insights into the authentication and login processes. Through the examination of these logs, I explored the mechanisms employed by the Windows operating system to detect and record attempted user logins, thereby understanding the intricate procedures and events involved in identifying and managing login attempts within the Windows environment:  <br/>
<img src="https://i.imgur.com/R1J9QY2.pngs"/>
<br />
<br />
I disabled the Windows Firewall within the Virtual Machine (VM) to temporarily suspend its network filtering and security mechanisms. This action involved accessing the Windows Firewall settings and deactivating the firewall to allow unrestricted network traffic to and from the VM, facilitating specific testing or configuration adjustments as needed:  <br/>
<img src="https://i.imgur.com/2MYkUDs.png"/>
<br />
<br />
I developed and employed a custom PowerShell script tailored for precise data collection purposes. To enhance geolocation data retrieval from live cyber attackers, I obtained an API key from Geolocation.io, integrating it into the script for accurate geographical information. Executing the script facilitated the real-time extraction of geo data from active cyber attackers, providing valuable insights into their geographic origins for comprehensive analysis and monitoring:  <br/>
<img src="https://i.imgur.com/qULu9yc.png"/>
<br />
<br />
I established a custom log configuration within the Log Analytics Workspace to facilitate the ingestion of specific data sets. Utilizing this setup, I refined and structured raw custom log data by creating custom fields, allowing for precise extraction and organization of pertinent information. This process enabled the transformation of raw data into actionable insights within the workspace, enhancing the analysis and interpretation of the custom log data:  <br/>
<img src="https://i.imgur.com/n52bA3I.png"/> 
<br />
<br />
I configured the map visualization within Azure Sentinel, integrating Latitude and Longitude data fields to geographically plot the origins of cyber attacks. By correlating these coordinates with specific country and city information, I enabled a comprehensive visual representation on the map, providing clear insights into the geographic locations of the incoming attacks, facilitating an understanding of attack origins by country and city within Azure Sentinel:  <br/>
<img src="https://i.imgur.com/tzQmu4e.png"/>
<br />
<br />

I fine-tuned the map plot sizes within Azure Sentinel to visually emphasize distinct data points, enabling a comprehensive observation of attack origins. Analyzing the geospatial data, several key takeaways emerged:

Universal Targeting: Hackers demonstrate a lack of specificity in their targets, indicating a universal approach, emphasizing the importance of robust security measures for all systems and data.

Administrator Password Security: The prevalence of common brute force techniques underscores the criticality of avoiding commonly used passwords, particularly for administrative access, to mitigate these predictable attack vectors.

Global Attack Landscape: The widespread distribution of attack attempts from various regions globally underscores the necessity for robust password policies and Multi-Factor Authentication (MFA) as essential layers of defense.

Notable Attack Origins: Analysis revealed notable concentrations of attack origins, particularly from Russia and East Africa, highlighting these regions as primary sources of attempted breaches against the VM, warranting focused attention and heightened security measures for these areas:  <br/>
<img src="https://i.imgur.com/LBotruM.png"/>
</p>

<!--
 ```diff
- text in red
+ text in green
! text in orange
# text in gray
@@ text in purple (and bold)@@
```
--!>
