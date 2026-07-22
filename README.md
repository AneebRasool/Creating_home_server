# Creating a home server

This will be a repo of me documenting a project that I have been wanting to do for a while, repurposing an old ~9 yr old laptop into a low budget server to learn the basics of using linux, file hosting, and learn valuable skills like trouble shooting. 

I hope to not only learn but to actually self host for control of my own data instead of relying on big companies to do the same thing, plus I am doing it for almost free! You may follow my journey to help yourself set up with a server.

**Current hardware:**
| Component | Specs |
|-----------|------|
| CPU | Intel i5-3230M 2.60Ghz, 2 Cores, 4 Threads |
| RAM | 4GB Ddr3|
| Disk | Hgst 512Gb Hdd |
| GPU | Intel Integrated Graphics 3rd Gen|
| Network | Built in ethernet / Qualcom Atheros QCA9565 Wifi Adapter|


Current goals:

- [x] Install a light weight OS (any good linux distro)
- [x] Set up a NAS to access with ideally no 3rd party software (from phone and PC)
- [x] Be able to use NAS outside of home (possibly via tailscale)


# End results?

The project really helped me manage all my files, from inside and outside my home. Its fast enough for most basic file transfers, and I learned a lot from this, like actually applying linux commands ive learned in the past like `sudo` or `nano`, how to install linux, and how to configure my own NAS with the `SMB` protocol, and for outside home using `Tailscale` which uses `wireguard`, a very secure protocol allowing me to transfer files securely and privately.

Reflecting on the project, the only major issue was having to carry my chunky computer to my main workplace, but I quickly learned about the wonders of `SSH`, and now I can control it from across the house!

Even though my main computer has 1tb of storage which is quite a lot, I have just 117GB of free space, and with google drive, onedrive, or other solutions giving just a few gigabytes for free (with honestly questionable level of privacy), this server that I have made is only accessible to me (and to whomever else I choose to share it to), and I get ~512GB of free storage forever, no monthly payments.

  <img width="637" height="105" alt="image" src="https://github.com/user-attachments/assets/e59193a2-efa8-4a44-b4e6-e3d355b032b9" />

As you can see, the server uses only about `12%` of my 4gb ram (or about `480MB`) of ram, compared to even `linux mint`, which I had installed before used `1.5GB` of ram! Before mint, I had `windows 10`, which took a massive `2.3GB`, many of the procces probably being privacy invasive microsoft telemetery, and background services that can't be disabled (that I probably wont use anyways). 
  
Some next steps that could be added here, one is definetely better hardware (the 100mbps ethernet limit is a huge bottleneck, everything else like the `hard drive`, even the `cpu` and the `ram` are not that bad. I get `~11MB/s` at home, not bad but could be definetely better... Which would probably mean shelling out some money for a new system, as reasonably no ethernet/wifi adapter would bring network speeds significantly to the old laptop, considering the old motherboard it would have. 

<img width="445" height="212" alt="image" src="https://github.com/user-attachments/assets/4739ef82-6da1-4829-b485-eb89892acdce" />



  


