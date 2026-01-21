<h1>Active Directory Lab Module 08: Patch and Endpoint Management with Action1</h1>

<p>
For this module of the lab, I created an Action1 account and connected it to my Windows Server 2022 domain controller by installing the Action1 agent on the server. My goal is to explore how Action1 supports patch management, endpoint management, security visibility, reporting, and auditing, and how these capabilities contribute to better compliance, system stability, and overall security in an organization.
</p>

<h2>Dashboard Overview</h2>
<p>
The Action1 dashboard provides a high level snapshot of the entire environment. It includes device status, patch compliance, vulnerabilities, and recent activity. It also highlights SLA related metrics such as overdue updates, devices falling behind patching policies, and endpoints that are out of compliance with defined update timelines. This makes it easy to identify where attention is needed and helps maintain alignment with organizational security and update expectations.
</p>
<p><img src="https://imgur.com/3UjLJG6.png" alt="Dashboard Overview"></p>

<h2>Real Time Reports and Alerts</h2>
<p>
Action1 includes several reporting tools that provide deep visibility into the environment. These provide live, on demand data about endpoints, installed software, vulnerabilities, update status, and configuration details.
</p>

<h3>Custom Reports</h3>
<p>
These allow the creation of tailored queries that can be saved and reused.
</p>
<p><img src="https://imgur.com/87xUcxx.png" alt="Custom Reports"></p>

<h3>Built in Reports</h3>
<p>
These include ready made views for common needs such as missing patches, software inventory, device activity, and compliance summaries.
</p>

<h2>IT Asset Management</h2>
<p>
The IT Asset Management section includes built in reports for software inventory, hardware inventory, and managed endpoints. These reports can be used for audits or documentation and can be expanded for more granular detail.
</p>
<p><img src="https://imgur.com/Kt3orRK.png" alt="IT Asset Management"></p>

<h3>Examples include:</h3>

<p>A list of all managed endpoints</p>
<p>
<img src="https://imgur.com/UX7Gl2X.png" alt="Managed Endpoints 1">
<img src="https://imgur.com/AMT52GP.png" alt="Managed Endpoints 2">
</p>

<p>A hardware summary across devices</p>
<p>
<img src="https://imgur.com/UaLJH27.png" alt="Hardware Summary 1">
<img src="https://imgur.com/Q3awas1.png" alt="Hardware Summary 2">
</p>

<p>A software inventory for compliance or licensing reviews</p>

<h2>Patch Management</h2>
<p>
The Patch Management section centralizes everything related to updates. This includes installed updates, missing updates, devices requiring reboots, overdue patches, Windows Update history, hotfixes, update status per device, and Windows 11 readiness checks. This provides a complete view of the update workflow and makes it easier to stay compliant, meet SLA timelines, and ensure every device remains secure and up to date.
</p>
<p><img src="https://imgur.com/ceVz4if.png" alt="Patch Management"></p>

<h2>Endpoint Security</h2>
<p>
The Endpoint Security section provides visibility into user and account activity across devices. It includes reports on users and groups, local group membership, local user accounts, logged on users, logon statistics, and profile information by user or computer. This helps identify unauthorized access, validate account configuration, troubleshoot login issues, and maintain a secure endpoint environment.
</p>
<p><img src="https://imgur.com/DXUhua0.png" alt="Endpoint Security"></p>

<h2>Endpoint Configuration</h2>
<p>
The Endpoint Configuration section gives you a clear look at how each device in your environment is set up. It pulls together details like system settings, network configuration, installed roles and features, and other technical information that helps you understand how your endpoints are actually built. This makes it easier to spot inconsistencies, troubleshoot configuration issues, and confirm that devices match the standards you expect. Instead of digging through each machine manually, Action1 puts all of this information in one place so you can quickly check whether everything is configured the way it should be.
</p>
<p><img src="https://imgur.com/wLfAcS2.png" alt="Endpoint Configuration"></p>

<h2>Vulnerability Management</h2>
<p>
The Vulnerability Management section focuses on the security risks across your devices and helps you understand which issues matter most. It shows all detected vulnerabilities, highlights the critical ones, and even calls out known exploited vulnerabilities so you can prioritize what needs attention. Each entry includes severity details and scoring to help you judge the impact. This section gives you a straightforward view of your overall security posture and makes it easier to plan your next steps, whether that is patching, investigating, or documenting compensating controls. It is a practical way to stay ahead of potential threats and keep your environment secure.
</p>
<p><img src="https://imgur.com/kh35DIc.png" alt="Vulnerability Management"></p>

<h2>Scheduled Reports</h2>
<p>
Any report can be automated and delivered on a recurring schedule. This is useful for tracking patch compliance, vulnerabilities, device health, and software changes without manually running reports.
</p>
<p><img src="https://imgur.com/xTrnvUp.png" alt="Scheduled Reports"></p>

<h2>Alerts</h2>
<p>
The Alerts section is where alert rules are created for overdue patches, new vulnerabilities, devices going offline, and failed updates. Since no alert rules were configured yet, the section displayed an empty state. Once rules are added, this area becomes a central place for monitoring urgent issues.
</p>
<p><img src="https://imgur.com/znWsfFq.png" alt="Alerts"></p>

<h2>Automations</h2>
<p>
Automations allow patching and script execution to run quietly in the background without disrupting users. In real environments, most updates install silently. Reboots are handled through maintenance windows or scheduled restarts. Devices may be woken with Wake on LAN or updated the next time they are online if they miss a scheduled window. By combining automated patching with controlled reboot policies, Action1 keeps systems secure and compliant while minimizing user impact.
</p>
<p><img src="https://imgur.com/QOJ80JI.png" alt="Automations"></p>

<h2>Patch Management Walkthrough on the Domain Controller</h2>

<p>
When I first installed the Action1 agent on my Server 2022 domain controller, the platform immediately surfaced missing patches and associated CVEs. This is expected because Microsoft cumulative updates contain many vulnerability fixes in a single package.
</p>
<p><img src="https://imgur.com/QwdiUHl.png" alt="Missing Patches"></p>

<h3>How cumulative updates affect vulnerability reporting</h3>
<ul>
  <li>A single cumulative update may resolve dozens of CVEs</li>
  <li>Out of date systems show large vulnerability clusters</li>
  <li>IT teams typically patch by installing the cumulative update rather than addressing CVEs individually</li>
  <li>Individual CVEs are reviewed only for special cases such as zero day issues or audit requests</li>
</ul>

<h3>Identifying and Deploying Updates</h3>
<p>
In the Missing Updates section, I identified two important updates:
</p>
<ul>
  <li>Windows cumulative update KB5073457</li>
  <li>.NET cumulative update KB5066743</li>
</ul>
<p><img src="https://imgur.com/jlO4LmH.png" alt="Missing Updates"></p>

<p>
These updates bring both the operating system and the .NET runtime up to date. When deploying updates, Action1 provides reboot options such as no automatic reboot, reboot if required, or display a message to logged in users. I also enabled the option to deactivate updates in Windows settings so Action1 fully controls patching instead of Windows Update.
</p>
<p><img src="https://imgur.com/CwXr3Rv.png" alt="Reboot Options"></p>

<p>
In production, domain controllers are rebooted during maintenance windows. In this lab, I allowed the reboot so the updates could apply immediately.
</p>
<p>
<img src="https://imgur.com/bTLRL9D.png" alt="Rebooting">
<img src="https://imgur.com/6PzwUdq.png" alt="Rebooting 2">
</p>

<p>
I used Run once and Run now because I wanted the cumulative updates to install immediately so I could verify that Action1 patching worked in real time. Since this is a lab with no active users, there was no need for a scheduled window. I left the completion deadline as is so the update would retry if the endpoint briefly went offline. Overall, these settings kept the process simple and let me confirm that manual patch deployment through Action1 was working correctly.
</p>
<p><img src="https://imgur.com/N1Wx44P.png" alt="Run Once Settings"></p>
<p><img src="https://imgur.com/eR0mpbK.png" alt="Run Now"></p>

<p>
During deployment, I confirmed the update process was running by checking Task Manager on the domain controller.
</p>
<p>
<img src="https://imgur.com/wUe723s.png" alt="Task Manager 1">
<img src="https://imgur.com/AvUvPEz.png" alt="Task Manager 2">
<img src="https://imgur.com/1B9LyIi.png" alt="Task Manager 3">
</p>

<h3>Automatic Defender Updates</h3>
<p>
After installing the cumulative updates, Action1 detected a Microsoft Defender Security Intelligence Update KB2267602. I did not deploy this manually. Action1 installed it automatically during the next update scan.
</p>
<p><img src="https://imgur.com/bSKPBED.png" alt="Defender Update"></p>

<p>
To verify this, I checked Event Viewer under Applications and Services Logs, then Microsoft, then Windows, then Windows Defender, and finally Operational. Event ID 2000 confirmed the Defender definition update was installed successfully. Defender updates use a separate update channel and do not require reboots.
</p>
<p><img src="https://imgur.com/MoV6byh.png" alt="Event Viewer"></p>

<h3>Secure Boot DBX Update</h3>
<p>
The final remaining update was KB5012170, the Secure Boot DBX standalone update. I deployed it through Action1, and the platform reported successful installation. Because this update requires Secure Boot, which is not supported in my virtualized environment, it may continue to appear as missing. This is normal for virtual machines. Action1 correctly evaluated the endpoint and marked it fully up to date based on what is applicable to the hardware.
</p>
<p>
<img src="https://imgur.com/FhBR3yG.png" alt="DBX Update 1">
<img src="https://imgur.com/XxjDQYi.png" alt="DBX Update 2">
<img src="https://imgur.com/XxqE2Vi.png" alt="DBX Update 3">
<img src="https://imgur.com/d6kzYOb.png" alt="DBX Update 4">
<img src="https://imgur.com/gcvrMYu.png" alt="DBX Update 5">
<img src="https://imgur.com/Ut36Q2J.png" alt="DBX Update 6">
</p>

<p>
Checking the dashboard, there were no remaining missing updates or vulnerabilities to attend to.
</p>
<p>
<img src="https://imgur.com/F0P1IFc.png" alt="Dashboard Clean">
<img src="https://imgur.com/jJ3aKa6.png" alt="Dashboard Clean 2">
</p>

<h2>Action1 Automatic Agent Deployment: What Made It Work in My Environment</h2>

<p>
To enable fully automated onboarding of domain joined devices, I configured Action1 so the platform could discover computers in Active Directory and silently deploy the agent without manual installation. The following components were essential to making this workflow function correctly.
</p>

<h3>1. Installed the Action1 Deployer on the Domain Controller</h3>
<p>
The deployer service on my Server 2022 domain controller is responsible for:
</p>
<ul>
  <li>Syncing the AD structure into Action1</li>
  <li>Discovering domain joined computers</li>
  <li>Using domain credentials to push the agent</li>
  <li>Running deployment cycles automatically every hour</li>
</ul>

<h3>2. Selected All Computers in Active Directory Domains or OUs</h3>
<p>
Instead of targeting a specific OU, I chose the option to deploy to all computers in Active Directory. This meant:
</p>
<ul>
  <li>Any domain joined machine automatically became eligible</li>
  <li>No OU movement or restructuring was required</li>
</ul>
<p>
<img src="https://imgur.com/LI2pxiD.png" alt="Deployment Settings 1">
<img src="https://imgur.com/n6I8n5S.png" alt="Deployment Settings 2">
</p>

<h3>3. Ensured the Domain Controller Provided Reliable DNS</h3>
<p>
For the deployer to authenticate to machines and for the agent to reach Action1 cloud, DNS needed to be stable. This included:
</p>
<ul>
  <li>The internal NIC using the DC for DNS</li>
  <li>The NAT NIC handling internet access</li>
  <li>Forwarders configured for external resolution</li>
  <li>AD DNS zones functioning normally</li>
</ul>

<h3>4. Verified Network Communication Between the DC and the Workstation</h3>
<p>
The deployer installs the agent using standard Windows management channels. To support this, I confirmed:
</p>
<ul>
  <li>The Windows 11 VM was joined to the domain</li>
  <li>The DC could reach the workstation by hostname</li>
  <li>Required services and firewall rules were in place</li>
</ul>

<h3>5. Allowed the Hourly Deployment Cycle to Run</h3>
<p>
Once everything was aligned, DNS, networking, AD visibility, and deployment rules, the Action1 Deployer automatically:
</p>
<ul>
  <li>Detected the Windows 11 VM</li>
  <li>Authenticated using domain credentials</li>
  <li>Copied the agent installer</li>
  <li>Installed it silently</li>
  <li>Registered the device with the Action1 cloud</li>
</ul>

<p>
The workstation then appeared in the console with full inventory and status reporting.
</p>

<h3>Result</h3>
<p>
With the environment properly configured, Action1 automatically deployed the agent to my Windows 11 VM without any manual installation, creating a realistic enterprise style workflow where new or reimaged devices are onboarded automatically the moment they join the domain. You can see here in the services of the Windows 11 VM the Action1 Agents are active.
</p>
<p>
<img src="https://imgur.com/8vxYp8v.png" alt="Agent Installed 1">
<img src="https://imgur.com/k1gX4y8.png" alt="Agent Installed 2">
</p>

<h2>Overview of Updates Detected on the Windows 11 VM</h2>

<p>
When reviewing the update status for the Windows 11 workstation (sharpPC) in Action1, three items appear in the Missing Updates list. Each one represents a different category of update, and not all of them require action. Here is a concise overview of what they are and how they behave.
</p>
<p><img src="https://imgur.com/jlQXuRf.png" alt="sharpPC Updates"></p>

<h3>1. .NET Framework Preview Update (KB5067931)</h3>
<p>
This is an optional preview update for the .NET Framework. Preview updates are early releases intended for testing and are not required for security or compliance. They do not install automatically and are normally skipped in production environments. This update can be safely ignored in the lab.
</p>

<h3>2. Microsoft OneDrive Client Update</h3>
<p>
Action1 is reporting that a newer version of the OneDrive sync client is available. OneDrive updates itself automatically in the background, so this item does not require manual deployment. It will eventually update on its own, and Action1 will reflect the new version after the next scan.
</p>

<h3>3. Security Intelligence Update for Microsoft Defender Antivirus (KB2267602)</h3>
<p>
This is a Defender definition update. These updates are released frequently and install automatically through the Defender update channel, even when Windows Update is disabled. Action1 will also apply them during its next scan. No manual action is needed.
</p>

<h3>Summary</h3>
<ul>
  <li>The .NET preview update is optional and can be ignored.</li>
  <li>The OneDrive update will update itself automatically.</li>
  <li>The Defender definition update installs automatically through its own channel.</li>
</ul>

<p>
None of these require manual deployment, and sharpPC is effectively up to date for all practical and security relevant purposes.
</p>

<p><img src="https://imgur.com/jlQXuRf.png" alt="sharpPC Summary"></p>
