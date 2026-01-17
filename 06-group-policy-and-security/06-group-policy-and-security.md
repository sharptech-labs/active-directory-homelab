<h1>Lets Create an OU Now, just a simple one, later we will create a business</h1>
<br /><br />

<h3>Open Active Directory Users and Computers</h3>
<br />

<h3>Right‑click your domain → New → Organizational Unit</h3>
<br />
<p align="center">
  <img src="https://imgur.com/Y7Epzzz.png" width="85%" />
</p>
<br /><br />

<h3>Name it: StandardUsers</h3>
<br />

<h3>Click OK</h3>
<br />
<p align="center">
  <img src="https://imgur.com/aWLGmbd.png" width="85%" />
</p>
<br /><br />

<h3>In Users, right-click your user, click Move, and select Standard Users</h3>
<br />
<p align="center">
  <img src="https://imgur.com/GLB0iwK.png" width="85%" />
</p>
<br /><br />

<h3>Click OK</h3>
<br />
<p align="center">
  <img src="https://imgur.com/mjhpxWc.png" width="85%" />
</p>
<br /><br />

<h1>Now We Will Create a Group</h1>
<br /><br />

<h3>Right‑click the StandardUsers OU</h3>
<br />
<p align="center">
  <img src="https://imgur.com/CUqTdSP.png" width="85%" />
</p>
<br /><br />

<h3>New → Group, and name it Standard Users</h3>
<br />
<p align="center">
  <img src="https://imgur.com/h17xLvs.png" width="85%" />
</p>
<br /><br />

<h3>Make sure these settings are applied , Group scope: Global, Group type: Security</h3>
<br />

<h3>Press OK</h3>
<br />

<h1>Lets Add Your User to This Group Now</h1>
<br /><br />

<h3>Inside the OU, right-click your user and press "Add to a group"</h3>
<br />
<p align="center">
  <img src="https://imgur.com/iwrgg66.png" width="85%" />
</p>
<br /><br />

<h3>Type Standard Users here and press OK</h3>
<br />
<p align="center">
  <img src="https://imgur.com/oMXX3RP.png" width="85%" />
</p>
<p align="center">
  <img src="https://imgur.com/iHre7Lk.png" width="85%" />
</p>
<br /><br />

<h3>We can check if he was added successfully by double-clicking the Standard Users group and clicking the "Members" box at the top</h3>
<br />
<p align="center">
  <img src="https://imgur.com/3QIRF6b.png" width="85%" />
</p>
<br /><br />

<h3>Your user should be listed here</h3>
<br />

<h3>Now Open Group Policy Management</h3>
<br />

<h3>Forest: (yourdomain)→Domains→(yourdomain)→StandardUsers OU</h3>
<br />
<p align="center">
  <img src="https://imgur.com/aXTO2hM.png" width="85%" />
</p>
<p align="center">
  <img src="https://imgur.com/7jq5BAj.png" width="85%" />
</p>
<br /><br />

<h3>Right-click Standard Users OU and select "Create a GPO in this domain, and Link it here"</h3>
<br />
<p align="center">
  <img src="https://imgur.com/hz2Cq8E.png" width="85%" />
</p>
<br /><br />

<h3>Name it Standard User Restrictions</h3>
<br />
<p align="center">
  <img src="https://imgur.com/Jbthlge.png" width="85%" />
</p>
<br /><br />

<h3>Press OK</h3>
<br />

<h1>Now Let's Add a Few Restrictions to This Ou</h1>
<br /><br />

<h3>Right-click the GPO and click Edit</h3>
<br />
<p align="center">
  <img src="https://imgur.com/ji5XlvL.png" width="85%" />
</p>
<br /><br />

<h3>Navigate through User Configurati0n→Policies→Administrative Templates→System→Ctrl+Alt+Del Option</h3>
<br />

<h3>Double-click "Remove Task Manager"</h3>
<br />
<p align="center">
  <img src="https://imgur.com/8Dk1PX5.png" width="85%" />
</p>
<br /><br />

<h3>On the left press Enabled, apply, and OK</h3>
<br />
<p align="center">
  <img src="https://imgur.com/tbM8Vb1.png" width="85%" />
</p>
<br /><br />

<h3>Now lets do another</h3>
<br />

<h3>Navigate through User Configurati0n→Policies→Administrative Templates→Control Panel</h3>
<br />

<h3>Double-click "Prohibit access to Control Panel and PC settings"</h3>
<br />
<p align="center">
  <img src="https://imgur.com/hmJeVj4.png" width="85%" />
</p>
<br /><br />

<h3>On the left press Enabled, apply, and OK</h3>
<br />
<p align="center">
  <img src="https://imgur.com/mxExzRn.png" width="85%" />
</p>
<br /><br />

<h1>Now We Will Go Back to Our Windows 11 Machine</h1>
<br /><br />

<h3>Log in as your user</h3>
<br />

<h3>Press the Windows Key+r and type cmd to the open command prompt</h3>
<br />
<p align="center">
  <img src="https://imgur.com/3CSySlf.png" width="85%" />
</p>
<br /><br />

<h3>Type gpupdate /force</h3>
<br />
<p align="center">
  <img src="https://imgur.com/caFcqWa.png" width="85%" />
</p>
<p align="center">
  <img src="https://imgur.com/Kc4RdcI.png" width="85%" />
</p>
<br /><br />

<h3>Sign out, and log back in as your user</h3>
<br />

<h3>Press the Windows Key+r and type cmd to the open command prompt</h3>
<br />

<h3>Type gpresult /r</h3>
<br />

<h3>Here you can see under "Applied Group Policy Objects" the "Standard User Restrictions" GPO that we made</h3>
<br />
<p align="center">
  <img src="https://imgur.com/65fskn5.png" width="85%" />
</p>
<br /><br />

<h3>Let's see if it worked fully by going to the top of the VM instance and pressing Input→Keyboard→Insert Ctrl-Alt-Del</h3>
<br />
<p align="center">
  <img src="https://imgur.com/p0IIVpi.png" width="85%" />
</p>
<br /><br />

<h3>There is usually an option here to open the task manager, but as you can see, it doesn't even appear anymore</h3>
<br />
<p align="center">
  <img src="https://imgur.com/dM0Py1X.png" width="85%" />
</p>
<br /><br />

<h3>Press Cancel</h3>
<br />

<h3>At the bottom of your screen click the search bar and type Control Panel</h3>
<br />
<p align="center">
  <img src="https://imgur.com/mWWTIBq.png" width="85%" />
</p>
<br /><br />

<h3>Click on it, and you'll see this message telling you that this operation has been cancelled</h3>
<br />
<p align="center">
  <img src="https://imgur.com/r5ASMcH.png" width="85%" />
</p>
<br /><br />

<h3>Our GPO worked!</h3>
<br />

<h1>Lets Create a More Realistic OU Structure Now</h1>
<br /><br />

<h3>On (your domain controller), open Active Directory Users and Computers.</h3>
<br />
<p align="center">
  <img src="https://imgur.com/BYPfBvU.png" width="85%" />
</p>
<br /><br />

<h3>In the left pane, right‑click your domain (e.g., sharptech.com).</h3>
<br />

<h3>Click New → Organizational Unit.</h3>
<br />
<p align="center">
  <img src="https://imgur.com/xrIjTJt.png" width="85%" />
</p>
<br /><br />

<h3>Name the OU: CleanFoodsMarket.</h3>
<br />
<p align="center">
  <img src="https://imgur.com/QJTGRB4.png" width="85%" />
</p>
<br /><br />

<h3>Right‑click CleanFoodsMarket → New → Organizational Unit.</h3>
<br />
<p align="center">
  <img src="https://imgur.com/NzeoMnq.png" width="85%" />
</p>
<br /><br />

<h3>Name the child OU: Accounting.</h3>
<br />
<p align="center">
  <img src="https://imgur.com/AqdUI2E.png" width="85%" />
</p>
<br /><br />

<h3>Right‑click Accounting → New → Organizational Unit.</h3>
<br />
<p align="center">
  <img src="https://imgur.com/tFFzqVj.png" width="85%" />
</p>
<br /><br />

<h3>Create the following three OUs inside Accounting:</h3>
<br />
<h3>Computers</h3>
<br />
<p align="center">
  <img src="https://imgur.com/Rs1PnJq.png" width="85%" />
</p>
<br /><br />
<h3>Printers</h3>
<br />
<p align="center">
  <img src="https://imgur.com/X6Bvl6N.png" width="85%" />
</p>
<br /><br />
<h3>Users</h3>
<br />
<p align="center">
  <img src="https://imgur.com/YHjoS77.png" width="85%" />
</p>
<br /><br />

<h3>Move the domain‑joined Accounting PC into: CleanFoodsMarket → Accounting → Computers.</h3>
<br />
<p align="center">
  <img src="https://imgur.com/wiMeCiG.png" width="85%" />
</p>
<p align="center">
  <img src="https://imgur.com/EGcelsP.png" width="85%" />
</p>
<br /><br />

<h3>Move your user account (e.g., Dima) into: CleanFoodsMarket → Accounting → Users.</h3>
<br />
<p align="center">
  <img src="https://imgur.com/qMZVfRE.png" width="85%" />
</p>
<p align="center">
  <img src="https://imgur.com/XOW4ird.png" width="85%" />
</p>
<br /><br />

<h3>Confirm the final OU structure:</h3>
<br />
<h3>CleanFoodsMarket</h3>
<br />
<h3>&nbsp;&nbsp;&nbsp;&nbsp;Accounting</h3>
<br />
<h3>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Computers</h3>
<br />
<h3>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Printers</h3>
<br />
<h3>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Users</h3>
<br />
<p align="center">
  <img src="https://imgur.com/Phhlzpf.png" width="85%" />
</p>
<br /><br />

<h1>Wallpaper Preparation</h1>
<br /><br />

<h3>On your real PC, open the wallpaper PNG file you plan to use.</h3>
<br />
<p align="center">
  <img src="https://imgur.com/aCyvz0f.png" width="85%" />
</p>
<br /><br />

<h3>Make sure image is 1920×1080, right click it and press Properties.</h3>
<br />
<p align="center">
  <img src="https://imgur.com/QgPb55W.png" width="85%" />
</p>
<p align="center">
  <img src="https://imgur.com/8z28OlW.png" width="85%" />
</p>
<br /><br />

<h3>Click OK.</h3>
<br />

<h3>Inside the Server 2022 VM, open File Explorer.</h3>
<br />

<h3>Navigate to the mapped drive pointing to your real PC’s shared folder.</h3>
<br />

<h3>Drag and drop the 1920×1080 PNG wallpaper into the Server 2022 VM.</h3>
<br />
<p align="center">
  <img src="https://imgur.com/v8ORH1r.png" width="85%" />
</p>
<br /><br />

<h1>Create &amp; Prepare Wallpaper Folder on (Your Domain Controller)</h1>
<br /><br />

<h3>On (your domain controller), open File Explorer.</h3>
<br />

<h3>Create the folder: C:\Wallpapers</h3>
<br />
<p align="center">
  <img src="https://imgur.com/CM5JYmo.png" width="85%" />
</p>
<p align="center">
  <img src="https://imgur.com/brq7Svk.png" width="85%" />
</p>
<br /><br />

<h3>Open the mapped drive again, copy YourWallpaper.png</h3>
<br />
<p align="center">
  <img src="https://imgur.com/k7MPimr.png" width="85%" />
</p>
<br /><br />

<h3>Paste your wallpaper PNG into C:\Wallpapers.</h3>
<br />
<p align="center">
  <img src="https://imgur.com/GBYh7iV.png" width="85%" />
</p>
<br /><br />

<h3>Confirm the file exists at: C:\Wallpapers\YourWallpaper.png</h3>
<br />

<h1>Share the Wallpaper Folder</h1>
<br /><br />

<h3>Right‑click C:\Wallpapers → Properties.</h3>
<br />
<p align="center">
  <img src="https://imgur.com/ru31fsQ.png" width="85%" />
</p>
<br /><br />

<h3>Click the Sharing tab.</h3>
<br />
<p align="center">
  <img src="https://imgur.com/Y5witzf.png" width="85%" />
</p>
<br /><br />

<h3>Click Advanced Sharing.</h3>
<br />
<p align="center">
  <img src="https://imgur.com/Y5witzf.png" width="85%" />
</p>
<br /><br />

<h3>Check Share this folder.</h3>
<br />

<h3>Set share name: Wallpapers</h3>
<br />

<h3>Click Permissions.</h3>
<br />
<p align="center">
  <img src="https://imgur.com/MpAJxbi.png" width="85%" />
</p>
<br /><br />

<h3>Click add and type Domain Users, then press OK.</h3>
<br />
<p align="center">
  <img src="https://imgur.com/R9I5RdK.png" width="85%" />
</p>
<p align="center">
  <img src="https://imgur.com/s4HrB7G.png" width="85%" />
</p>
<br /><br />

<h3>Click Apply.</h3>
<br />
<p align="center">
  <img src="https://imgur.com/qShclHa.png" width="85%" />
</p>
<br /><br />

<h3>Click OK, then Apply again, OK, Close.</h3>
<br />
<p align="center">
  <img src="https://imgur.com/P4oxtTQ.png" width="85%" />
</p>
<p align="center">
  <img src="https://imgur.com/5beoNtj.png" width="85%" />
</p>
<p align="center">
  <img src="https://imgur.com/kOW0ALP.png" width="85%" />
</p>
<br /><br />

<h3>Confirm the UNC path works: \\(your domain controller)\Wallpapers\YourWallpaper.png</h3>
<br />
<p align="center">
  <img src="https://imgur.com/jy4Zzgb.png" width="85%" />
</p>
<br /><br /><h1>Create the Wallpaper GPO</h1>
<br /><br />

<h3>Open Group Policy Management.</h3>
<br />
<p align="center">
  <img src="https://imgur.com/D0ouAqw.png" width="85%" />
</p>
<br /><br />

<h3>Expand the domain and locate: CleanFoodsMarket → Accounting → Computers.</h3>
<br />

<h3>Right‑click Computers → Create a GPO in this domain, and Link it here…</h3>
<br />
<p align="center">
  <img src="https://imgur.com/jJr6nwI.png" width="85%" />
</p>
<br /><br />

<h3>Name it: Accounting-Desktop-Wallpaper.</h3>
<br />
<p align="center">
  <img src="https://imgur.com/12DlMK7.png" width="85%" />
</p>
<br /><br />

<h3>Click OK.</h3>
<br />

<h1>Enable Loopback Processing</h1>
<br /><br />

<h3>Right‑click Accounting-Desktop-Wallpaper → Edit.</h3>
<br />
<p align="center">
  <img src="https://imgur.com/JhPLYpF.png" width="85%" />
</p>
<br /><br />

<h3>Expand Computer Configuration.</h3>
<br />

<h3>Expand Policies → Administrative Templates.</h3>
<br />
<p align="center">
  <img src="https://imgur.com/8fD9HNO.png" width="85%" />
</p>
<br /><br />

<h3>Expand System.</h3>
<br />

<h3>Click Group Policy.</h3>
<br />
<p align="center">
  <img src="https://imgur.com/y02iIDM.png" width="85%" />
</p>
<br /><br />

<h3>Double‑click Configure User Group Policy loopback processing mode.</h3>
<br />

<h3>Select Enabled.</h3>
<br />
<p align="center">
  <img src="https://imgur.com/7lm5z1u.png" width="85%" />
</p>
<br /><br />

<h3>Set Mode to Merge.</h3>
<br />
<p align="center">
  <img src="https://imgur.com/kkoxvgb.png" width="85%" />
</p>
<br /><br />

<h3>Click Apply, then OK.</h3>
<br />
<p align="center">
  <img src="https://imgur.com/mo4xLhf.png" width="85%" />
</p>
<br /><br />

<h1>Enable “Always Wait for the Network”</h1>
<br /><br />

<h3>In the same GPO editor, expand Computer Configuration again.</h3>
<br />

<h3>Expand Administrative Templates.</h3>
<br />

<h3>Expand System.</h3>
<br />

<h3>Click Logon.</h3>
<br />

<h3>Double‑click Always wait for the network at computer startup and logon.</h3>
<br />
<p align="center">
  <img src="https://imgur.com/zGw2zFz.png" width="85%" />
</p>
<br /><br />

<h3>Select Enabled.</h3>
<br />

<h3>Click Apply, then OK.</h3>
<br />
<p align="center">
  <img src="https://imgur.com/J8s0nQf.png" width="85%" />
</p>
<p align="center">
  <img src="https://imgur.com/U8eF6cG.png" width="85%" />
</p>
<br /><br />

<h1>Configure the Wallpaper Setting</h1>
<br /><br />

<h3>In the same GPO editor, expand User Configuration.</h3>
<br />

<h3>Expand Policies→Administrative Templates.</h3>
<br />

<h3>Expand Desktop.</h3>
<br />

<h3>Click Desktop.</h3>
<br />
<p align="center">
  <img src="https://imgur.com/jc2BHI2.png" width="85%" />
</p>
<br /><br />

<h3>Double‑click Desktop Wallpaper.</h3>
<br />
<p align="center">
  <img src="https://imgur.com/EilayNG.png" width="85%" />
</p>
<br /><br />

<h3>Select Enabled.</h3>
<br />

<h3>Enter the UNC path: \\(your domain controller)\Wallpapers\YourWallpaper.png</h3>
<br />

<h3>Set wallpaper style to Fill.</h3>
<br />
<p align="center">
  <img src="https://imgur.com/E0K16dp.png" width="85%" />
</p>
<br /><br />

<h3>Click Apply, then OK.</h3>
<br />
<p align="center">
  <img src="https://imgur.com/8qilnrH.png" width="85%" />
</p>
<br /><br />

<h1>Verify GPO Link</h1>
<br /><br />

<h3>In Group Policy Management, confirm Accounting-Desktop-Wallpaper is linked to: CleanFoodsMarket → Accounting → Computers.</h3>
<br />
<p align="center">
  <img src="https://imgur.com/F1piCFp.png" width="85%" />
</p>
<br /><br /><h1>Create Accounting Share Folder</h1>
<br /><br />

<h3>On (your domain controller), open File Explorer.</h3>
<br />

<h3>Create the folder: C:\AccountingShare</h3>
<br />
<p align="center">
  <img src="https://imgur.com/OovzKdZ.png" width="85%" />
</p>
<p align="center">
  <img src="https://imgur.com/gTFlTxu.png" width="85%" />
</p>
<br /><br />

<h1>Set NTFS Permissions on Accounting Share</h1>
<br /><br />

<h3>Right‑click C:\AccountingShare → Properties.</h3>
<br />
<p align="center">
  <img src="https://imgur.com/wqaADzC.png" width="85%" />
</p>
<br /><br />

<h3>Click the Security tab.</h3>
<br />

<h3>Click Edit.</h3>
<br />
<p align="center">
  <img src="https://imgur.com/tJdxxG9.png" width="85%" />
</p>
<br /><br />

<h3>Click Add.</h3>
<br />
<p align="center">
  <img src="https://imgur.com/LszBkmb.png" width="85%" />
</p>
<br /><br />

<h3>Type Domain Users.</h3>
<br />

<h3>Click Check Names.</h3>
<br />

<h3>Click OK.</h3>
<br />
<p align="center">
  <img src="https://imgur.com/dK9QHoM.png" width="85%" />
</p>
<br /><br />

<h3>Select Domain Users.</h3>
<br />

<h3>Check Read &amp; execute.</h3>
<br />

<h3>Check List folder contents.</h3>
<br />

<h3>Check Read.</h3>
<br />

<h3>Click Apply then OK.</h3>
<br />
<p align="center">
  <img src="https://imgur.com/qs19aj3.png" width="85%" />
</p>
<p align="center">
  <img src="https://imgur.com/iSduEQ3.png" width="85%" />
</p>
<br /><br />

<h3>Press Close.</h3>
<br />

<h1>Share the Accounting Share Folder</h1>
<br /><br />

<h3>Right‑click C:\AccountingShare → Properties.</h3>
<br />
<p align="center">
  <img src="https://imgur.com/vPEJ6ql.png" width="85%" />
</p>
<br /><br />

<h3>Click the Sharing tab.</h3>
<br />

<h3>Click Advanced Sharing.</h3>
<br />
<p align="center">
  <img src="https://imgur.com/iMqpfri.png" width="85%" />
</p>
<br /><br />

<h3>Check Share this folder.</h3>
<br />

<h3>Set share name: AccountingShare</h3>
<br />

<h3>Click Permissions.</h3>
<br />
<p align="center">
  <img src="https://imgur.com/MUX9G5T.png" width="85%" />
</p>
<br /><br />

<h3>Click add and type Domain Users, then press OK.</h3>
<br />
<p align="center">
  <img src="https://imgur.com/duVnypT.png" width="85%" />
</p>
<p align="center">
  <img src="https://imgur.com/Yenislp.png" width="85%" />
</p>
<br /><br />

<h3>Press Apply, then OK.</h3>
<br />
<p align="center">
  <img src="https://imgur.com/s31Tqpp.png" width="85%" />
</p>
<p align="center">
  <img src="https://imgur.com/ppDdFzF.png" width="85%" />
</p>
<br /><br />

<h3>Press Apply again, OK, then Close.</h3>
<br />
<p align="center">
  <img src="https://imgur.com/j4q82Mu.png" width="85%" />
</p>
<p align="center">
  <img src="https://imgur.com/jfgtG1K.png" width="85%" />
</p>
<br /><br />

<h3>Confirm the UNC path: \\(your domain controller)\AccountingShare</h3>
<br />
<p align="center">
  <img src="https://imgur.com/kURqvWP.png" width="85%" />
</p>
<br /><br />

<h1>Create the Logon Script in SYSVOL</h1>
<br /><br />

<h3>On (your domain controller), open File Explorer.</h3>
<br />

<h3>Navigate to: \\(your domain controller)\SYSVOL\yourdomain.com\scripts</h3>
<br />
<p align="center">
  <img src="https://imgur.com/dZRUeUA.png" width="85%" />
</p>
<p align="center">
  <img src="https://imgur.com/LrfYb7E.png" width="85%" />
</p>
<p align="center">
  <img src="https://imgur.com/AETRgAR.png" width="85%" />
</p>
<br /><br />

<h3>Right‑click → New → Text Document.</h3>
<br />
<p align="center">
  <img src="https://imgur.com/LhhHkoT.png" width="85%" />
</p>
<br /><br />

<h3>Name it AccountingLogon.txt.</h3>
<br />
<p align="center">
  <img src="https://imgur.com/y1kqdcH.png" width="85%" />
</p>
<br /><br />

<h3>In File Explorer → View → Options.</h3>
<br />
<p align="center">
  <img src="https://imgur.com/Sxeqrq2.png" width="85%" />
</p>
<br /><br />

<h3>Click the View tab.</h3>
<br />

<h3>Uncheck Hide extensions for known file types</h3>
<br />
<p align="center">
  <img src="https://imgur.com/CWh56Xg.png" width="85%" />
</p>
<br /><br />

<h3>Click Apply.</h3>
<br />
<p align="center">
  <img src="https://imgur.com/N51coCV.png" width="85%" />
</p>
<br /><br />

<h3>Click OK.</h3>
<br />
<p align="center">
  <img src="https://imgur.com/dgHyZbL.png" width="85%" />
</p>
<br /><br />

<h3>Rename AccountingLogon.txt to: AccountingLogon.bat</h3>
<br />
<p align="center">
  <img src="https://imgur.com/OakpccW.png" width="85%" />
</p>
<p align="center">
  <img src="https://imgur.com/IQOUBP0.png" width="85%" />
</p>
<br /><br />

<h3>Click Yes when warned.</h3>
<br />
<p align="center">
  <img src="https://imgur.com/oMD4LfT.png" width="85%" />
</p>
<br /><br />

<h3>Right‑click AccountingLogon.bat → Edit→Run.</h3>
<br />
<p align="center">
  <img src="https://imgur.com/G2149oq.png" width="85%" />
</p>
<p align="center">
  <img src="https://imgur.com/g2Sr1Z4.png" width="85%" />
</p>
<br /><br />

<h3>Enter:</h3>
<br />

<h3>net use H: \\(your domain controller)\AccountingShare /persistent:no</h3>
<br />
<p align="center">
  <img src="https://imgur.com/eaClomY.png" width="85%" />
</p>
<br /><br />

<h3>Save and close Notepad.</h3>
<br />
<p align="center">
  <img src="https://imgur.com/P4x4aXw.png" width="85%" />
</p>
<br /><br />

<h3>Confirm the script remains in the SYSVOL scripts folder.</h3>
<br />
<p align="center">
  <img src="https://imgur.com/ndG9sG1.png" width="85%" />
</p>
<br /><br /><h1>Attach the Logon Script to the Wallpaper GPO</h1>
<br /><br />

<h3>In Group Policy Management, right‑click Accounting-Desktop-Wallpaper → Edit.</h3>
<br />
<p align="center">
  <img src="https://imgur.com/Tnk2ZVJ.png" width="85%" />
</p>
<br /><br />

<h3>Expand User Configuration → Policies.</h3>
<br />

<h3>Expand Windows Settings.</h3>
<br />

<h3>Click Scripts (Logon/Logoff).</h3>
<br />

<h3>Double‑click Logon.</h3>
<br />
<p align="center">
  <img src="https://imgur.com/dkGfU4U.png" width="85%" />
</p>
<br /><br />

<h3>Click Add.</h3>
<br />
<p align="center">
  <img src="https://imgur.com/Bqpwl7r.png" width="85%" />
</p>
<br /><br />

<h3>Click Browse.</h3>
<br />
<p align="center">
  <img src="https://imgur.com/nhlJAVR.png" width="85%" />
</p>
<br /><br />

<h3>Select AccountingLogon.bat.</h3>
<br />

<h3>Click Open.</h3>
<br />
<p align="center">
  <img src="https://imgur.com/6GcGaPs.png" width="85%" />
</p>
<br /><br />

<h3>Confirm Script Name = AccountingLogon.bat.</h3>
<br />

<h3>Leave Script Parameters empty.</h3>
<br />

<h3>Click OK.</h3>
<br />
<p align="center">
  <img src="https://imgur.com/bUqErAT.png" width="85%" />
</p>
<br /><br />

<h3>Click Apply, then OK again.</h3>
<br />
<p align="center">
  <img src="https://imgur.com/97rkDE9.png" width="85%" />
</p>
<p align="center">
  <img src="https://imgur.com/09i0bD6.png" width="85%" />
</p>
<br /><br />

<h1>Verify GPO Scope Again</h1>
<br /><br />

<h3>Confirm Accounting-Desktop-Wallpaper is still linked to: CleanFoodsMarket → Accounting → Computers.</h3>
<br />
<p align="center">
  <img src="https://imgur.com/TpDFAnn.png" width="85%" />
</p>
<br /><br />

<h1>Update Group Policy on the Client</h1>
<br /><br />

<h3>On the Accounting PC, press Win + R.</h3>
<br />

<h3>Type cmd.</h3>
<br />

<h3>Press Enter.</h3>
<br />
<p align="center">
  <img src="https://imgur.com/rlyXgWU.png" width="85%" />
</p>
<br /><br />

<h3>Type: gpupdate /force</h3>
<br />

<h3>Press Enter.</h3>
<br />
<p align="center">
  <img src="https://imgur.com/0o2EeIQ.png" width="85%" />
</p>
<br /><br />

<h3>Wait for the update to complete.</h3>
<br />
<p align="center">
  <img src="https://imgur.com/JugQ58r.png" width="85%" />
</p>
<br /><br />

<h3>Log off.</h3>
<br />
<p align="center">
  <img src="https://imgur.com/Rft46te.png" width="85%" />
</p>
<br /><br />

<h1>Final Test</h1>
<br /><br />

<h3>Log back in as your user.</h3>
<br />

<h3>Confirm the wallpaper loads correctly.</h3>
<br />

<h3>Open File Explorer.</h3>
<br />

<h3>Click This PC.</h3>
<br />

<h3>Confirm the H: drive is mapped to: \\(your domain controller)\AccountingShare</h3>
<br />
<p align="center">
  <img src="https://imgur.com/HAIT8bD.png" width="85%" />
</p>
<br /><br />

<h1>Optional Verification</h1>
<br /><br />

<h3>Press Win + R.</h3>
<br />

<h3>Type cmd.</h3>
<br />

<h3>Click OK.</h3>
<br />
<p align="center">
  <img src="https://imgur.com/BxBzVRP.png" width="85%" />
</p>
<br /><br />

<h3>Type: gpresult /r</h3>
<br />

<h3>Press Enter.</h3>
<br />
<p align="center">
  <img src="https://imgur.com/n6gMTlb.png" width="85%" />
</p>
<br /><br />

<h3>Confirm Accounting-Desktop-Wallpaper appears under Applied Group Policy Objects.</h3>
<br />
<p align="center">
  <img src="https://imgur.com/IaTSpC6.png" width="85%" />
</p>
<br /><br />
