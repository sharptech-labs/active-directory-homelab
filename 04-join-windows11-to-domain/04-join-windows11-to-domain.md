<h1>Joining a Windows 11 Machine to a Windows Server 2022 Domain</h1>

<br />

<h3>Start the Windows Server 2022 VM in VirtualBox and log in.</h3>
<br />

<p align="center">
  <img src="https://imgur.com/h1D0Frx.png" width="85%" />
</p>

<p align="center">
  <img src="https://imgur.com/pAfAa2z.png" width="85%" />
</p>

<br />
<br />

<h3>Open Devices → Network → Network Settings.</h3>
<br />

<p align="center">
  <img src="https://imgur.com/T7ISdlL.png" width="85%" />
</p>

<br />
<br />

<h3>Select “Host‑only Adapter” from the dropdown.</h3>
<br />

<p align="center">
  <img src="https://imgur.com/pt49ndx.png" width="85%" />
</p>

<br />
<br />

<h3>Open Control Panel → Network and Internet → Network and Sharing Center.</h3>
<br />

<p align="center">
  <img src="https://imgur.com/tKkmtzO.png" width="85%" />
</p>

<br />
<br />

<h3>Click “Change adapter settings” on the left.</h3>
<br />

<br />
<br />

<h3>Click “Ethernet” → Properties.</h3>
<br />

<p align="center">
  <img src="https://imgur.com/J1eAxdJ.png" width="85%" />
</p>

<br />
<br />

<h3>Double‑click “Internet Protocol Version 4 (TCP/IPv4)”.</h3>
<br />

<p align="center">
  <img src="https://imgur.com/vhPSMno.png" width="85%" />
</p>

<br />
<br />

<h3>Select “Use the following IP address” and enter your server’s static IP.</h3>
<br />

<p align="center">
  <img src="https://imgur.com/0bzqaf6.png" width="85%" />
</p>

<br />
<br />

<h3>Click OK and close all windows.</h3>
<br />

<p align="center">
  <img src="https://imgur.com/56YLOdd.png" width="85%" />
</p>

<br />
<br />

<h3>Start your Windows 11 VM and log in.</h3>
<br />

<br />
<br />

<h3>Open Network and Sharing Center again.</h3>
<br />

<p align="center">
  <img src="https://imgur.com/MsN9Lbg.png" width="85%" />
</p>

<br />
<br />

<h3>Click “Change adapter settings”.</h3>
<br />

<br />
<br />

<h3>Click “Ethernet” → Properties.</h3>
<br />

<br />
<br />

<h3>Double‑click “Internet Protocol Version 4 (TCP/IPv4)”.</h3>
<br />

<p align="center">
  <img src="https://imgur.com/HoCLytG.png" width="85%" />
</p>

<br />
<br />

<h3>Select “Use the following IP address” and enter your Windows 11 static IP.</h3>
<br />

<p align="center">
  <img src="https://imgur.com/J1Ecu9f.png" width="85%" />
</p>

<br />
<br />

<h3>Open Devices → Network → Network Settings.</h3>
<br />

<p align="center">
  <img src="https://imgur.com/zk7Fj08.png" width="85%" />
</p>

<br />
<br />

<h3>Select “Host‑only Adapter”.</h3>
<br />

<p align="center">
  <img src="https://imgur.com/FVmdm5D.png" width="85%" />
</p>

<br />
<br />

<h3>Click OK and close all windows.</h3>
<br />

<br />
<br />

<h3>Open Command Prompt and ping your domain name.</h3>
<br />

<p align="center">
  <img src="https://imgur.com/SmJ3CnV.png" width="85%" />
</p>

<br />
<br />

<h3>Open File Explorer → click “This PC” → Properties.</h3>
<br />

<p align="center">
  <img src="https://imgur.com/rDkqcsF.png" width="85%" />
</p>

<br />
<br />

<h3>Click “Domain or workgroup”.</h3>
<br />

<p align="center">
  <img src="https://imgur.com/RvxP8gb.png" width="85%" />
</p>

<br />
<br />

<h3>Click “Change”, select “Domain”, and enter your domain name.</h3>
<br />

<p align="center">
  <img src="https://imgur.com/iZeVD4h.png" width="85%" />
</p>

<p align="center">
  <img src="https://imgur.com/iMsxcZi.png" width="85%" />
</p>

<br />
<br />

<h3>Enter administrator credentials when prompted.</h3>
<br />

<br />
<br />

<h3>Click OK, close System Properties, and restart the VM.</h3>
<br />

<p align="center">
  <img src="https://imgur.com/Q2efu9g.png" width="85%" />
</p>

<p align="center">
  <img src="https://imgur.com/ibSUnJ5.png" width="85%" />
</p>

<br />
<br />

<h3>On the Server 2022 VM, open Server Manager → Tools → Active Directory Users and Computers.</h3>
<br />

<p align="center">
  <img src="https://imgur.com/VWg25vN.png" width="85%" />
</p>

<br />
<br />

<h3>Verify the Windows 11 machine appears under “Computers”.</h3>
<br />

<p align="center">
  <img src="https://imgur.com/4XXcfvI.png" width="85%" />
</p>

<br />
<br />

<h3>On the Windows 11 login screen, select “Other user”.</h3>
<br />

<br />
<br />

<h3>Enter the domain username and password you created.</h3>
<br />

<p align="center">
  <img src="https://imgur.com/FH9zSOE.png" width="85%" />
</p>

<br />
<br />

<h3>You are now logged into the domain‑joined Windows 11 machine.</h3>
<br />

