# Active Directory Setup

## Rename the Server

Inside your Windows Server 2022 VM, navigate to **Server Manager**, select **Local Server** on the left bar, click the computer name, and press **Change**.

Name it what you choose — I used **OR‑DC‑01** for Oregon Domain Controller 01.

![Image](https://imgur.com/K7xNNNZ.png)

Restart the server.

---

## Install Active Directory Domain Services (AD DS)

In Server Manager, navigate to **Manage** at the top right, select **Add Roles and Features**, and click **Next** until the **Active Directory Domain Services** option appears under *Server Roles*. Select it.

![Image](https://imgur.com/u1D6fsQ.png)

Press **Add Features**, then click **Next** until the option to **Install** appears, and click it.

Select **Promote this server to a domain controller**.

![Image](https://imgur.com/u1D6fsQ.png)

Select **Add a new forest** — I named mine **sharptech.com**.

Create a **DSRM password**.

![Image](https://imgur.com/rqCMBFn.png)

For the purposes of this lab, press **Next** until installation begins.

Restart the server.

---

## Install VirtualBox Guest Additions

Select **Devices** from the top left of the Server 2022 instance and click **Insert Guest Additions CD Image…**

![Image](https://imgur.com/LCBKJs0.png)
![Image](https://imgur.com/JdoXclR.png)

Navigate to **File Explorer**, click the CD drive, and double‑click the **amd64 installer**.

Restart the server.

---

## Configure Shared Folders

Select **Devices** → **Shared Folders** → **Shared Folders Settings**.

![Image](https://imgur.com/MA5XgdV.png)

To map a folder from your local PC, press **Add New Shared Folder**, click **Other**, and select the folder path.  
You can create a dedicated folder on your PC for this — I made mine **sharptechshare**.

Check **Make Permanent** and **Auto‑Mount**.

![Image](https://imgur.com/OwFqyxY.png)
![Image](https://imgur.com/j1B0hRH.png)

---

# Adding a User in Active Directory

In Server Manager, click **Tools** in the top‑right and select **Active Directory Users and Computers**.  
![Image](https://imgur.com/8VaK5MB.png)

In the left pane right‑click **Users** → **New** → **User**.  
![Image](https://imgur.com/r4rCLfI.png)

Enter the user’s full name and their logon name.  
![Image](https://imgur.com/1MEUuuZ.png)

Create a password. For this lab, uncheck **User must change password at next logon**.  
![Image](https://imgur.com/YFzGhdS.png)

After the user is created, double‑click the account to open its properties.  
Here you can configure details such as logon hours, address, organization info, account options, and more.  
![Image](https://imgur.com/grXteHS.png)

By right‑clicking the user, you can disable the account, reset the password, or add the user to groups.  
![Image](https://imgur.com/IgMvxUS.png)

I also created my own user account, which I will later add to the **Domain Admins** group to make it an administrator account for the remainder of the lab.  
*(No image)*

