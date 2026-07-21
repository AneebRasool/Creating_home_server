### Entry 2: installing & configuring ubuntu
Date: July 21 2026

Now that I have decided I want to use `ubuntu server LTS` for long term support for the OS, I can now begin installing.

- Step 1: Downloading the ISO and creating a bootable USB.

Install the ISO file from `https://ubuntu.com/server`. Select how you want to download, and download it to your computer. 

Install Rufus (to create a bootable usb using your iso) you can grab it from `https://rufus.ie/en/`

<img width="476" height="589" alt="image" src="https://github.com/user-attachments/assets/fb6b59c4-294a-4176-ae3c-f28c158472db" />

After clicking start and letting Rufus format your drive, your USB drive is ready to boot into Ubuntu Server.

- Step 2: Installing Ubuntu to the server computer.

Its time to finally install ubuntu. `also if you can, plug into ethernet from now so that ubuntu server can install drivers now` Plug in your USB into the laptop/pc, and restart. Now you need to mash a button to open up the boot loader menu. (On my HP laptop its `f9`), but can be different like `F10`, `f11`, `esc` etc so search it up for your motherboard or laptop brand.

Once you find the button, it should boot into a menu that lists boot options:

<img width="4000" height="2468" alt="20260721_123959" src="https://github.com/user-attachments/assets/769fa5e8-c51a-45a1-ae8e-c2efb899228e" />

From the menu select whichever shows up as your hard drive, for me it is USB Hard drive. After entering, you will be taken to the linux bootloader, `grub`.

Then there should be 3 options on a black screen, simply enter into `Try or install Ubuntu Server`, and it should begin installing. 

After its done, there will be a welcome screen and will walk you through basic config choices, pretty self explanatory (like language, or if you want to install ubuntu server (minimized) or not, I just leave it default).

Now if you have ethernet connected you will get a screen like this:
<img width="4000" height="3000" alt="20260721_131005" src="https://github.com/user-attachments/assets/c0bacd5a-8fad-45f7-8945-284148d27e6a" />


Thats a good sign, means that ubuntu found that you are using, continue. You can then setup proxy (if needed). Then you will get an option for mirror adress, you can leave it at default. For storage layout, select which drive you want to install to, but everything else I leave default (as I dont need to encrypt my drive). 

<img width="4000" height="3000" alt="20260721_131518" src="https://github.com/user-attachments/assets/7ff9bdc0-2eb4-446c-ba3e-6009d282d339" />

Once you get to here, you can leave everything default if it checks out, continue.

You will then be asked to initialize your name, servername, username, password keep those in mind, I wrote them down on google docs just in case as it will be used to access the pc. You can then choose to get ubuntu pro, I skipped, and if you want to use openSSH server, you can. I chose to install it now so if I want later I can have it pre installed. You can then install server snaps, then after you press done, it will begin installing. Just wait for a reboot now option, and it will reboot. 

Once its done everything, you will go to the main screen, asking for your login. You put your username, then password, and congrats, ubuntu server is oficially installed!

<img width="4000" height="3000" alt="20260721_140937" src="https://github.com/user-attachments/assets/99dca3c7-fd11-48c2-b691-bc96ba027e89" />

- step 3: post install configurations. 

I would first run `sudo apt update`, to update any packages that are avalible.

Now if you are like me, you probably want to close the lid without the computer turning off, we can do that with some commands and editing a config file.

first type `sudo nano /etc/systemd/logind.comf` then enter.
<img width="4000" height="3000" alt="20260721_141748" src="https://github.com/user-attachments/assets/3e00db61-c7ae-4f1d-b199-5c589a6d13e3" />
Once you see this on your screen, scroll down to `#HandleLidSwitch=suspend`. 

Change: 

`#HandleLidSwitch=suspend` --> `HandleLidSwitch=ignore`
`#HandleLidSwitchExternalPower=suspend` --> `HandleLidSwitchExternalPower=ignore`
`#HandleLidSwitchDocked=ignore` --> `HandleLidSwitchDocked=ignore`

Then press `CTRL + O`, then `enter`, then, `CTRL + X` to exit. 

Now after restarting the server pc, just to be sure everything works you can ping your computer to see if the connection works. You can run the command `ping 192.168.2.x` on an alternate pc in command prompt. (to find out your server's ip adress, type in `hostname -I`. 

One last thing that I want to do is to use SSH, basically allowing me to run commands from my main pc which controls the server pc, without having to be next to it all the time. Its very secure as well! As I installed openSSH while setting up, I simply have to connect it from my windows pc. Il be setting it up using a password, as I wont be doing any port forwarding or such to expose it to the network, but you could use keys to make it more secure.

on your alternative pc, in command prompt or terminal, type `ssh user@192.168.2.x` where the ip adress (of your linux pc) is after the @ and your linux server's username is before the @. type yes if it prompts anythying, and it works!







