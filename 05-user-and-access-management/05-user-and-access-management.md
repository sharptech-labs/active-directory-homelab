<h1>User and Access Management</h1>

<br />

<h3>First I am going to make my own user a Domain Admin as stated in the last module.</h3>

<br />
<br />

<h3>Start both your Windows Server 2022 VM and Windows 11 VM.</h3>

<br />
<br />

<h3>On your domain controller, open Server Manager.</h3>

<br />
<br />

<h3>Select Tools.</h3>

<br />

<p align="center">
  <img src="https://imgur.com/yDQQPED.png" width="85%" />
</p>

<br />
<br />

<h3>Click Active Directory Users and Computers.</h3>

<br />
<br />

<h3>Go to the Users container.</h3>

<br />
<br />

<h3>Find the user you want to elevate (for this I am making myself a Domain Admin).</h3>

<br />

<p align="center">
  <img src="https://imgur.com/zXdAjFy.png" width="85%" />
</p>

<br />
<br />

<h3>Right‑click the user and click Properties.</h3>

<br />

<p align="center">
  <img src="https://imgur.com/GGReokM.png" width="85%" />
</p>

<br />
<br />

<h3>Go to the "Member Of" tab and click Add.</h3>

<br />

<p align="center">
  <img src="https://imgur.com/dDKEXex.png" width="85%" />
</p>

<br />
<br />

<h3>Type "Domain Admins".</h3>

<br />

<p align="center">
  <img src="https://imgur.com/ZLqSfyu.png" width="85%" />
</p>

<br />
<br />

<h3>Click OK, Apply, OK.</h3>

<br />

<p align="center">
  <img src="https://imgur.com/2HvloLD.png" width="85%" />
</p>

<br />
<br />

<h3>Now we can confirm I was added by going to Builtin, and clicking the Administrators Security Group.</h3>

<br />

<p align="center">
  <img src="https://imgur.com/SGQe9qu.png" width="85%" />
</p>

<br />
<br />

<h3>Select the box "Members" and double-click Domain Admins.</h3>

<br />

<p align="center">
  <img src="https://imgur.com/GfeFOut.png" width="85%" />
</p>

<br />
<br />

<h3>In the Domain Admin properties click "Members" and you should see your name listed there.</h3>

<br />

<p align="center">
  <img src="https://imgur.com/BlNRsw7.png" width="85%" />
</p>

<br />
<br />

<h3>Now let's practice some account management for the user you created in module 03.</h3>

<br />
<br />

<h3>In your domain, click on Users and double-click the user you created.</h3>

<br />

<p align="center">
  <img src="https://imgur.com/jy9lyc3.png" width="85%" />
</p>

<br />
<br />

<h3>Click the Account tab, and click "Logon Hours".</h3>

<br />

<p align="center">
  <img src="https://imgur.com/KnZiHxS.png" width="85%" />
</p>

<p align="center">
  <img src="https://imgur.com/WJsvcp1.png" width="85%" />
</p>

<br />
<br />

<h3>Here we can specify exactly what times they are able to log in to their account.</h3>

<br />

<p align="center">
  <img src="https://imgur.com/V9f9mER.png" width="85%" />
</p>

<br />
<br />

<h3>Click the times you desire (I chose a current timeframe for demonstration) and then press "Logon Denied" to make that box white.</h3>

<br />
<br />

<h3>Press OK, then Apply.</h3>

<br />

<p align="center">
  <img src="https://imgur.com/Ppn309X.png" width="85%" />
</p>

<br />
<br />

<h3>On your Windows 11 machine, enter that user's username and password and attempt to log in.</h3>

<br />

<p align="center">
  <img src="https://imgur.com/P8ywi1I.png" width="85%" />
</p>

<br />
<br />

<h3>You should see this message, indicating your change worked.</h3>

<br />

<p align="center">
  <img src="https://imgur.com/Y7YbIy0.png" width="85%" />
</p>

<br />
<br />

<h3>At this point you can go back into your Windows Server 2022 and restore those logon times to continue this lab.</h3>

<br />
<br />

<h3>Now let's see what happens if we make this account expire on a certain date.</h3>

<br />
<br />

<h3>Back in Server 2022, with your user's account still open, at the bottom section "Account expires" select "End of".</h3>

<br />

<p align="center">
  <img src="https://imgur.com/TyGNpd6.png" width="85%" />
</p>

<br />
<br />

<h3>From the calendar drop down, just set a date in the past for the purposes of this lab.</h3>

<br />

<p align="center">
  <img src="https://imgur.com/O82pdCi.png" width="85%" />
</p>

<br />
<br />

<h3>Press Apply.</h3>

<br />

<p align="center">
  <img src="https://imgur.com/f8o6a9q.png" width="85%" />
</p>

<br />
<br />

<h3>On your Windows 11 machine, try to log in to the user's account.</h3>

<br />

<p align="center">
  <img src="https://imgur.com/W3HnyRd.png" width="85%" />
</p>

<br />
<br />

<h3>You should get this message.</h3>

<br />

<p align="center">
  <img src="https://imgur.com/R166C5g.png" width="85%" />
</p>

<br />
<br />

<h3>To continue the lab, go back to Server 2022 and select "Never" in the user's account and click Apply.</h3>

<br />
<br />

<h3>Let's reset the user's password.</h3>

<br />
<br />

<h3>Back in your domain, right-click the user's name and select Reset Password.</h3>

<br />

<p align="center">
  <img src="https://imgur.com/E6B6p2w.png" width="85%" />
</p>

<br />
<br />

<h3>Set a new temporary password for them and make sure "User must change password at next logon" is checked.</h3>

<br />

<p align="center">
  <img src="https://imgur.com/6tTz2wf.png" width="85%" />
</p>

<p align="center">
  <img src="https://imgur.com/GvRVQyL.png" width="85%" />
</p>

<br />
<br />

<h3>At this point you would send this temporary password to the user over a secure channel.</h3>

<br />
<br />

<h3>Back on your Windows 11 machine, log in as that user using the temporary password and you'll (they'll) be prompted to make a new one.</h3>

<br />

<p align="center">
  <img src="https://imgur.com/MiDvnTL.png" width="85%" />
</p>

<p align="center">
  <img src="https://imgur.com/7aWQsN2.png" width="85%" />
</p>

<br />
<br />

<h3>This ensures only they know their final password, you’re not storing or remembering anyone’s credentials, and the account stays secure.</h3>

<br />
<br />

<h3>Create a new password for the user (the user themselves would do this).</h3>

<br />

<p align="center">
  <img src="https://imgur.com/hGhFzBz.png" width="85%" />
</p>

<p align="center">
  <img src="https://imgur.com/nuMLAEY.png" width="85%" />
</p>

<br />
<br />
