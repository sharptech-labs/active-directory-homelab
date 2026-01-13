# Joining a Windows 11 Machine to a Windows Server 2022 Domain

Start the Windows Server 2022 VM in VirtualBox and log in.  
![Image](https://imgur.com/h1D0Frx.png)  
![Image](https://imgur.com/pAfAa2z.png)

Open Devices → Network → Network Settings.  
![Image](https://imgur.com/T7ISdlL.png)

Select “Host‑only Adapter” from the dropdown.  
![Image](https://imgur.com/pt49ndx.png)

Open Control Panel → Network and Internet → Network and Sharing Center.  
![Image](https://imgur.com/tKkmtzO.png)

Click “Change adapter settings” on the left.  
*(No image)*

Click “Ethernet” → Properties.  
![Image](https://imgur.com/J1eAxdJ.png)

Double‑click “Internet Protocol Version 4 (TCP/IPv4)”.  
![Image](https://imgur.com/vhPSMno.png)

Select “Use the following IP address” and enter your server’s static IP.  
![Image](https://imgur.com/0bzqaf6.png)

Click OK and close all windows.  
![Image](https://imgur.com/56YLOdd.png)

Start your Windows 11 VM and log in.  
*(No image)*

Open Network and Sharing Center again.  
![Image](https://imgur.com/MsN9Lbg.png)

Click “Change adapter settings”.  
*(No image)*

Click “Ethernet” → Properties.  
*(No image)*

Double‑click “Internet Protocol Version 4 (TCP/IPv4)”.  
![Image](https://imgur.com/HoCLytG.png)

Select “Use the following IP address” and enter your Windows 11 static IP.  
![Image](https://imgur.com/J1Ecu9f.png)

Open Devices → Network → Network Settings.  
![Image](https://imgur.com/zk7Fj08.png)

Select “Host‑only Adapter”.  
![Image](https://imgur.com/FVmdm5D.png)

Click OK and close all windows.  
*(No image)*

Open Command Prompt and ping your domain name.  
![Image](https://imgur.com/SmJ3CnV.png)

Open File Explorer → click “This PC” → Properties.  
![Image](https://imgur.com/rDkqcsF.png)

Click “Domain or workgroup”.  
![Image](https://imgur.com/RvxP8gb.png)

Click “Change”, select “Domain”, and enter your domain name.  
![Image](https://imgur.com/iZeVD4h.png)  
![Image](https://imgur.com/iMsxcZi.png)

Enter administrator credentials when prompted.  
*(No image)*

Click OK, close System Properties, and restart the VM.  
![Image](https://imgur.com/Q2efu9g.png)  
![Image](https://imgur.com/ibSUnJ5.png)

On the Server 2022 VM, open Server Manager → Tools → Active Directory Users and Computers.  
![Image](https://imgur.com/VWg25vN.png)

Verify the Windows 11 machine appears under “Computers”.  
![Image](https://imgur.com/4XXcfvI.png)

On the Windows 11 login screen, select “Other user”.  
*(No image)*

Enter the domain username and password you created.  
![Image](https://imgur.com/FH9zSOE.png)

You are now logged into the domain‑joined Windows 11 machine.  
*(No image)*

