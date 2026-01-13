<h1>Windows 11 VM Setup</h1>

<br />

<h3>First download the Windows 11 installation media.</h3>
<br />

<p align="center">
  <img src="https://imgur.com/VJF6JIW.png" width="85%" />
</p>

<br />
<br />

<h3>Run the MediaCreationTool.exe.</h3>
<br />

<p align="center">
  <img src="https://imgur.com/VZHsU4K.png" width="85%" />
</p>

<br />
<br />

<h3>Press Next, then choose ISO file and save it to your desired location.</h3>
<br />

<p align="center">
  <img src="https://imgur.com/149JK7w.png" width="85%" />
</p>

<br />
<br />

<h3>In VirtualBox, press New, and name it Windows 11, then select the path for the ISO.</h3>
<br />

<br />
<br />

<h3>In specific virtual hardware I chose 4GB of RAM and 2 CPUs, 128 MB of video memory, and make sure to add enough storage to install Windows 11 properly — at least 64 GB, I did 100 GB.</h3>
<br />

<p align="center">
  <img src="https://imgur.com/cOuAIoW.png" width="85%" />
</p>

<br />
<br />

<h3>Press Finish.</h3>
<br />

<br />
<br />

<h3>Start the machine and begin the setup process.</h3>
<br />

<br />
<br />

<h3>Due to limitations of VirtualBox, you may get an error such as “The PC must support TPM 2.0” or “The PC must support Secure Boot” during the setup process.</h3>
<br />
There is a separate process to fix this that I will not show in detail here.  
Shortly, you can download Rufus and create an ISO that skips TPM and Secure Boot checks, then use the Microsoft Imaging and Deployment Tools Environment as part of the Windows Assessment and Deployment Kit (ADK) to create a bootable ISO image, and use this to boot your Windows 11 VM.

<br />
<br />

<h3>Select your desired settings, select Install Windows 11, and check “I agree.”</h3>
<br />

<p align="center">
  <img src="https://imgur.com/zEte28n.png" width="85%" />
</p>

<br />
<br />

<h3>Select “I don't have a product key.”</h3>
<br />

<br />
<br />

<h3>Select Windows 11 Pro, as you cannot join a domain with Windows 11 Home. Click Accept.</h3>
<br />

<p align="center">
  <img src="https://imgur.com/XsPHqz0.png" width="85%" />
</p>

<br />
<br />

<h3>Click Next on the storage drive, then press Install.</h3>
<br />

<p align="center">
  <img src="https://imgur.com/gl8DJVM.png" width="85%" />
</p>

<br />
<br />

<h3>Navigate to Machine → Settings → Network. Choose Bridged Adapter under “Attached to,” and select “Allow VMs” under Promiscuous Mode. This will allow internet to the machine.</h3>
<br />

<p align="center">
  <img src="https://imgur.com/wfhC8dz.png" width="85%" />
</p>

<br />
<br />

<h3>After the install, navigate through the setup process and name your computer.</h3>
<br />

<br />
<br />

<h3>It will reboot, then choose “Set up for Personal Use.”</h3>
<br />

<p align="center">
  <img src="https://imgur.com/pxbMyLa.png" width="85%" />
</p>

<br />
<br />

<h3>Press Sign‑in and follow steps to create a new account.</h3>
<br />

<p align="center">
  <img src="https://imgur.com/CT2rrQf.png" width="85%" />
</p>

<p align="center">
  <img src="https://imgur.com/xTrWYXq.png" width="85%" />
</p>

<br />
<br />

<h3>Select “Set up as new PC” and click Next.</h3>
<br />

<p align="center">
  <img src="https://imgur.com/YCwuE3Q.png" width="85%" />
</p>

<br />
<br />

<h3>Skip the next two screens, press Accept, then decline Microsoft 365.</h3>
<br />

<br />
<br />

<h3>Skip again, and right‑click the disc icon at the bottom right of the VM instance and press “Remove Disk From Virtual Machine.”</h3>
<br />

<br />
<br />

<h3>You are in your Windows 11 machine!</h3>
<br />

<br />
<br />

<h3>To make the display larger, select Devices from the top left of the VM instance and click “Insert Guest Additions CD Image…” from the dropdown.</h3>
<br />

<br />
<br />

<h3>Navigate to File Explorer and click the CD drive, then double‑click the VBoxWindowsAdditions.exe file.</h3>
<br />

<br />
<br />

<h3>Reboot, then from the top left of the VM instance click View → Auto‑resize Guest Display. Adjust the resolution to your liking now within Windows 11.</h3>
<br />

