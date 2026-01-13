<h1>Active Directory Setup</h1>

<br />

<h3>Inside your Windows Server 2022 VM, navigate to Server Manager, select Local Server on the left bar, click the computer name, and press Change.</h3>
<br />

<br />
<br />

<h3>Name it what you choose — I used OR‑DC‑01 for Oregon Domain Controller 01.</h3>
<br />

<p align="center">
  <img src="https://imgur.com/K7xNNNZ.png" width="85%" />
</p>

<br />
<br />

<h3>Restart the server.</h3>
<br />

<br />
<br />

<h3>In Server Manager, navigate to Manage at the top right, select Add Roles and Features, and click Next until the Active Directory Domain Services option appears under Server Roles. Select it.</h3>
<br />

<p align="center">
  <img src="https://imgur.com/u1D6fsQ.png" width="85%" />
</p>

<br />
<br />

<h3>Press Add Features, then click Next until the option to Install appears, and click it.</h3>
<br />

<br />
<br />

<h3>Select Promote this server to a domain controller.</h3>
<br />

<p align="center">
  <img src="https://imgur.com/u1D6fsQ.png" width="85%" />
</p>

<br />
<br />

<h3>Select Add a new forest — I named mine sharptech.com.</h3>
<br />

<br />
<br />

<h3>Create a DSRM password.</h3>
<br />

<p align="center">
  <img src="https://imgur.com/rqCMBFn.png" width="85%" />
</p>

<br />
<br />

<h3>For the purposes of this lab, press Next until installation begins.</h3>
<br />

<br />
<br />

<h3>Restart the server.</h3>
<br />

<br />
<br />

<h3>Select Devices from the top left of the Server 2022 instance and click Insert Guest Additions CD Image… from the dropdown.</h3>
<br />

<p align="center">
  <img src="https://imgur.com/LCBKJs0.png" width="85%" />
</p>

<p align="center">
  <img src="https://imgur.com/JdoXclR.png" width="85%" />
</p>

<br />
<br />

<h3>Navigate to File Explorer, click the CD drive, and double‑click the amd64 installer shown there.</h3>
<br />

<br />
<br />

<h3>Restart the server.</h3>
<br />

<br />
<br />

<h3>Select Devices from the top left of the Server 2022 instance and click Shared Folders → Shared Folders Settings.</h3>
<br />

<p align="center">
  <img src="https://imgur.com/MA5XgdV.png" width="85%" />
</p>

<br />
<br />

<h3>To map a folder from your local PC, press Add New Shared Folder (the folder icon with a green plus), click Other, and select the folder path. You can create a dedicated folder on your PC for this — I made mine sharptechshare.</h3>
<br />

<br />
<br />

<h3>Check Make Permanent and Auto‑Mount.</h3>
<br />

<p align="center">
  <img src="https://imgur.com/OwFqyxY.png" width="85%" />
</p>

<p align="center">
  <img src="https://imgur.com/j1B0hRH.png" width="85%" />
</p>

<br />
