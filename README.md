<h1>Threat Detection Lab using Microsoft Sentinel</h1>


<h2>Description</h2>
This lab focuses on building custom threat detection logic in Microsoft Sentinel by creating a scheduled analytics rule to monitor failed logon attempts using Event ID 4625. In addition, this lab demonstrates the use of writing a Kusto Query Language (KQL) query to detect multiple failed login events, configure alert thresholds, and set up event grouping to correlate related incidents. The objective is to gain hands-on experience with Microsoft Sentinel’s detection capabilities, improving the ability to identify potential brute-force or unauthorized access attempts within a cloud-native SOC environment.

<img width="1520" height="674" alt="Image" src="https://github.com/user-attachments/assets/29564ec3-c480-4d68-bdf8-fc9e2bbf4f8d" />

<h2>This lab covers:</h2>

- <b>Custom Threat Detection Logic: Creating scheduled analytics rules in Microsoft Sentinel to detect suspicious activity.</b>
- <b>Monitoring Failed Logon Attempts: Using Event ID 4625 to identify potential brute-force or unauthorized access attempts.</b>
- <b>Kusto Query Language (KQL): Writing and applying KQL queries to filter and analyze security event data.</b>
- <b>Alert Thresholds and Event Grouping: Configuring alert logic and grouping related events for more accurate and actionable detections.</b>
- <b>Cloud-Native SOC Operations: Gaining hands-on experience with Microsoft Sentinel in a simulated Security Operations Center (SOC) environment.</b>



<h2>Utilities Used:</h2>

- <b>Microsoft Azure Portal: The main interface for managing Azure resources, including setting up Sentinel, configuring scheduled analytics rules, and managing log data.</b>
- <b>Microsoft Sentinel: A cloud-native SIEM (Security Information and Event Management) solution used for building detection rules, monitoring events, and managing incidents.</b>
- <b>Log Analytics Workspace: Backend service that stores and queries log data ingested by Microsoft Sentinel. It’s where the analytics rules and KQL queries are executed.</b> 
- <b>Kusto Query Language (KQL): Used to write custom queries for detecting security events like failed logon attempts (Event ID 4625).</b>
- <b>Security Event Logs (Event ID 4625): Windows event logs related to failed logon attempts; ingested into Sentinel via data connectors.</b>
- <b>Sentinel Analytics Rules Wizard: A step-by-step utility within Sentinel for creating scheduled query rules, defining conditions, setting alert thresholds, and configuring event grouping.</b>

<h2>Program walk-through:</h2>

<p align="center">Navigate to "Microsoft Sentinel" in the Azure portal. Select "Analytics" and select "Create" and "Scheduled query rule".</p> 

<img width="1899" height="865" alt="Image" src="https://github.com/user-attachments/assets/a249baeb-7c3f-47a6-9cb0-1c6b60564d03" />

<p align="center">Name your analytics rule. Set your severity level. Select "Initial Access" for the MITRE ATT&CK field.</p> 

<img width="1510" height="689" alt="Image" src="https://github.com/user-attachments/assets/bf7b0fdb-0f1a-4cde-94f3-2adddf86cb06" />

<p align="center">Under "Initial Access", select T1078 - "Valid Accounts" and ensure all accounts are selected. Select "Next" to set the rule logic.</p> 

<img width="1512" height="685" alt="Image" src="https://github.com/user-attachments/assets/1d9496b2-bed7-49d9-8441-432f30de3a22" />

<p align="center">Add rule query.</p> 

<img width="1508" height="656" alt="Image" src="https://github.com/user-attachments/assets/cd8735fb-c2e9-43b7-8eac-608a5c8404b3" />

<p align="center">Configure query scheduling. Ensure you select "Automatically" under "Start Running".</p> 

<img width="1497" height="661" alt="Image" src="https://github.com/user-attachments/assets/b30cbf5d-a654-455b-805e-2792f11059c5" />

<p align="center">Configure your "Alert Threshold" and "Event Grouping".</p> 

<img width="1506" height="648" alt="Image" src="https://github.com/user-attachments/assets/6eb4a887-5ed2-4670-9dcb-6ac0ee9010a1" />

<p align="center">Navigate back to the top of the page and select "Test with current data".</p> 

<img width="1494" height="648" alt="Image" src="https://github.com/user-attachments/assets/463bb7ed-f949-4c8f-828d-76094e08c78d" />

<p align="center">Results from the simulation. Notice that there is a total of 72K events that occurred in the past 14 days. </p> 

<img width="1884" height="805" alt="Image" src="https://github.com/user-attachments/assets/51f6cec9-e674-4c5b-9041-6751f1cb1974" />

<p align="center">Navigate to the bottom of the page and select "Next: Incident settings".</p> 

<img width="1497" height="650" alt="Image" src="https://github.com/user-attachments/assets/887a493d-9f08-4665-9de2-32c99e88ca99" />

<p align="center">Ensure you select "Enabled" to create incidents from alerts triggered by this analytical rule. Select "Next: Automated Response".</p> 

<img width="1497" height="648" alt="Image" src="https://github.com/user-attachments/assets/8f682523-fc3d-49a0-8127-242b0a42821e" />

<p align="center">You can create automation rules for your scheduled rule. For this lab, we will continue to "Next: Review + Create".</p> 

<img width="1502" height="648" alt="Image" src="https://github.com/user-attachments/assets/acc3ba28-84af-494c-9de8-a4445fabb4cd" />

<p align="center">Once validation has passed, select "Save".</p> 

<img width="1512" height="677" alt="Image" src="https://github.com/user-attachments/assets/c028d6ae-c1d8-4edc-a0c9-3f9df70d280a" />

<p align="center">Scheduled rule created.</p> 

<img width="1514" height="670" alt="Image" src="https://github.com/user-attachments/assets/adb8dc35-d3f7-42ad-891f-69c313bed431" />

<p align="center">Under "Threat Management", select "Incidents".</p> 

<img width="1512" height="668" alt="Image" src="https://github.com/user-attachments/assets/42b40391-6025-46c9-8a06-a3528819dac8" />

<p align="center">Your incidents will appear here. You can view full details and investigate the properties of each incident, and close the incident once the issue has been resolved.</p> 

<img width="1518" height="692" alt="Image" src="https://github.com/user-attachments/assets/4fcaf669-f3a1-470a-984b-9f2f83043b0a" />

<h2>Conclusion</h2>
This lab demonstrated how to create custom threat detection logic in Microsoft Sentinel by leveraging scheduled analytics rules and Kusto Query Language (KQL). By monitoring Windows Event ID 4625, we were able to detect failed logon attempts, which is an essential indicator of potential brute-force or unauthorized access attempts. This lab also covered configuring alert thresholds and event grouping, key features that enhance detection accuracy and reduce alert fatigue. Overall, this lab provided valuable insights on how Microsoft Sentinel can build effective, cloud-native threat detection workflows within a modern Security Operations Center (SOC) environment.


