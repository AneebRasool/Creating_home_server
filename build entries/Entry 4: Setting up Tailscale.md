### Entry 4: Setting up Tailscale
Date: July 21 2026

Its finally time to install Tailscale, so I can use the power of my server from anywhere in the world (if it works properly of course). Anyways getting started seems to be simple enough.

Before I started, I went to tailscales website and signed up using my google account. 

- Step 1: Installing tailscale on the linux pc

```bash
curl -fsSL https://tailscale.com/install.sh | sh
```
then

```bash
sudo tailscale up
```

After you run these 2, you will get a link that you will have to paste on another pc. I pasted it to my main pc, signed in again with my main pc and it added the linux pc to my account. I then downloaded tailscale for windows, signed in with my same google account and it added it to my account as well. I also got the android app so I can access on the go from my phone too.

When I got to the main screen of tailscale, it was very intuative, it had all the ip adresses ready to go. 

<img width="1899" height="952" alt="Screenshot 2026-07-21 204926" src="https://github.com/user-attachments/assets/b12adaa7-6beb-45bf-bf39-d62509cc62a9" />

The setup for my server with smb was also really the same as before (entry 3), for windows I had to do the same steps, map the network drive but this time with the IP adress they gave me for my linux server. I did the same from my phone in `CX file explorer` (great file manager by the way), where I set it up as an SMB network under new location, the password and username is the same as the user of your linux server, and password for smb.

To test it, I went on my phone, turned off wifi and used my mobile data, to access files (from cx file explorer) while tailscale ran in the background. Lo and behold, it worked! The latency as to be expected was a bit more than usual but now I can securely access my files from outside my home, a more secure google drive!




