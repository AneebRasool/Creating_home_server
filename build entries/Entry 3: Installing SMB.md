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






  
