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

After its done, there will be a welcome screen and will walk you through basic config choices, pretty self explanatory (like language) select what you prefer.

Once you get to Choose the base for the installation screen, you can choose whichever 



