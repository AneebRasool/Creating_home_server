### Entry 3: installing SMB
Date: July 21 2026

Now that I have ubuntu server up and running, with SSH I can just use my main windows 11 computer to access the server. You can still run the same commands from the linux computer directly, if you did not configure ssh but it is a lot more convinient.

- Step 1: Install samba.

  To install samba, run the following command and enter yes whenever it asks.
```bash
 sudo apt install samba 
```
- Step 2: create a directory

  to create a directory, you can use the `mkdir` command. For example, `mkdir /home/your user/LinuxCloud/`. You could use this folder to share (after configuring samba).

- Step 3: initialize/setup samba

  now that samba is installed we have to configure as by default its read only (but I want to read and write to and from it). run `sudo nano /etc/samba/smb.conf` and scroll all the way to the bottom. add this to the bottom:

```bash
[Your Custom Name]
    path = /home/aneeb/LinuxCloud/
    read only = no
    browsable = yes
```

now to save and exit press `CTRL + O`, then `enter`, then to exit `CTRL + X`.

Now to restart samba:

```bash
sudo service smbd restart
```

Just in case allow samba through the firewall:

```bash
sudo ufw allow samba
```

- Step 4: Set up a password for SMB

You can do this with the command: `sudo smbpasswd -a YOURUSER` just make sure to change YOURUSER to your actual username.

- Step 5: Mounting the drive to file explorer.

This can be done on mac and linux too, but im focusing on windows 11 as that is my main OS (could be linux in the future who knows)

First open up your `File Explorer`. Head over to `This PC` --> `Three dots` --> `Map Network Drive`

<img width="1536" height="817" alt="Screenshot 2026-07-21 174920" src="https://github.com/user-attachments/assets/a3186296-b061-4833-a900-ed62aa4a7a10" />

Enter your ip adress in the foler area, so 2 back slashes and your ip adress then click browse and it should pop up. You then click on the folder that shares, ok, then finish. I have the password saved, but if it asks for your user and password, enter your linux username and your password you created with the passwd command.

<img width="1257" height="685" alt="image" src="https://github.com/user-attachments/assets/d20e1b18-27dd-4a3f-a804-c0de2bc956c3" />

Now once you finish, under network locations you will see your server, which will use SMB. If you chose to save your password with windows credentials, you wont have to re enter it, and accessing your files will be as easy as clicking on it, and dragging and dropping what you want!

<img width="1135" height="679" alt="image" src="https://github.com/user-attachments/assets/e0abf397-dbe2-4305-9dd4-928a68663177" />







  
