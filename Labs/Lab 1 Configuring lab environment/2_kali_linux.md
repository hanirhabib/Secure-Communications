# Downloading and using Kali Linux

Kali Linux by **Offensive Security** is the distro of choice for penetration testers and other security professionals. Kali comes pre-loaded with 100s of useful security tools,scripts and wordlists. There are however plenty of other options also aimed towards security professionals, with Parrot OS or Black Arch Linux two of the popular alternatives.

For this module I'm going to be using Kali Linux but any modern Linux distro should be perfectly fine and allow you to install any of the required tools and to complete all the module labs and assignments. So you are free to choose your own preferred Linux distro. 

> :warning: Again, I won't be troubleshooting any issues outside of the suggested lab environment, and all examples/ demos will assume you are using the recommended setup.

We'll be running Kali as a virtual machine in VMWare, however you could also use Kali as a **live CD**, as part of a **dual-boot** setup, or even as your main **host OS**. While Kali is a great OS it's probably not the best choice as your main OS if you're planning on using it for everyday browsing and tasks. To quote the Kali Linux documentation:

> The fact of the matter is, however, that Kali is a Linux distribution specifically geared towards professional penetration testers and security specialists, and given its unique nature, it is NOT a recommended distribution if you're unfamiliar with Linux or are looking for a general-purpose Linux desktop distribution for development, web design, gaming, etc.

Likewise I strongly suggest using a VM versus a dual-boot setup, Simply because sometimes you want to switch between different OSs for different tools etc.

> :bulb: An alternative setup could be to use **Win-KeX** which essentially integrates Kali as an app on Windows 10. I haven't had enough time to test out this setup properly, but the latest version looks very promising, and has some potential benefits over using a VM. Check it out: [https://www.kali.org/news/win-kex-version-2-0/](https://www.kali.org/news/win-kex-version-2-0/)



## Getting Kali Linux

![Kali logo](./images/kali_logo.png)

On the Kali Linux download page [(https://www.kali.org/downloads/)](https://www.kali.org/downloads/) there are lots of different images available to suit whatever you need, however to ease the installation step a little I'm going to suggest we use the pre-built VMWare VM.

We can find the pre-built images on the Offensive Security VM Download Page [https://www.kali.org/get-kali/#kali-virtual-machines](https://www.kali.org/get-kali/#kali-virtual-machines) and select the **Kali Linux VMware 64-Bit** VM to download. (I'm using version 2021.2)

> :warning: The downloaded file is a 7-zip compressed file so you'll need to extract it before you can use it. You can easily download and install 7-zip if you need it. 

## Opening Kali with VMWare Workstation Pro

Once you have downloaded and extracted the Kali VM we need to open it with VMWare. So open VMWare, and choose the **Open a Virtual Machine** option. You'll be asked for the file location of the VM, so navigate to the extracted folder and choose the **.vmx** file.

> :writing_hand: For me this was Kali-Linux-2021.2-vmware-amd64.vmx

Once opened you'll have the option to **Power on this virtual machine** so choose this and when prompted select **I copied it**. The VM should now start booting up for us.

> :bulb: You might want to **Edit virtual machine settings** to tweak your settings.

## Logging into Kali Linux

If everything has gone to plan you should now be looking at the Kali login screen. We are now going to login and apply some updates and tweaks to our new Kali VM.

![Kali login](./images/kali_login.png)

> :writing_hand: the default username/password for the pre-built VM is kali/kali 
