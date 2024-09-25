
# Tweaking our Kali Setup 

Because we are using a pre-built VM some of the settings that we would normally configure during the installation process will need to be updated. 

> :bulb: If you've decided to do a fresh install rather than using the pre-built image then you've likely covered some of these steps during the installation process.

## 1. Keyboard Layout and Time-Zone
unless you prefer using a US keyboard layout, you probably want to change your Keyboard Layout before continuing.

You can either do that by going to the settings menu and searching for keyboard, or, you can just do it from the Terminal:

```bash
sudo dpkg-reconfigure keyboard-configuration
```

After choosing a layout of your liking you have to restart the service:

```bash
sudo service keyboard-setup restart
```

The easiest way to update your timezone is to right click on the system clock and select properties and use **Europe/Dublin** as your timezone to correct your system clock.


## 2. Changing the default SSH key and password

Our kali image uses a default username/password and uses a common SSH key, we'll want to change this ASAP as it leaves our VM extremely vulnerable.

We can change the password by simply typing the **passwd** command in the terminal. It will prompt for our current password and then the new password we wish to use.

Next on our list are the pre-generated ssh keys installed on the pre-built VM. After all we're all good at this security stuff right???? We don't want the same keys as the next person do we (MITM).....

Move the default Kali ssh keys to a new folder:

```bash
kali@kali:~$ cd /etc/ssh/
kali@kali:/etc/ssh/$ sudo mkdir default_kali_keys
kali@kali:/etc/ssh/$ sudo mv ssh_host_* default_kali_keys/
```
This will move your default keys to the new folder...  
Next we want to regenerate the keys:

```bash
kali@kali:/etc/ssh$ sudo dpkg-reconfigure openssh-server
Creating SSH2 RSA key; this may take some time ...  
3072 SHA256:rU4Cmp+mQ/YcP6lfwcUW6XHGoEKssS5jeLqYhf56gpk root@kali (RSA)  
Creating SSH2 ECDSA key; this may take some time ...  
256 SHA256:+oQOtnwR/yONrp2rQZ+btr5u+z04ZpbMChWHS+AF4zc root@kali (ECDSA)  
Creating SSH2 ED25519 key; this may take some time ...  
256 SHA256:sewxzogdIU25n8azANKWBk/1cmHdoHG1RIckL47RhcQ root@kali (ED25519)  
rescue-ssh.target is a disabled or a static unit, not starting it.  
/lib/runit-helper/runit-helper: 74: sv: not found
```

## 3. Creating a New User Account
Since Kali 2020.1, Kali now comes with a low privileged user account by default (the kali user). This is much better than the older root by default, and normally this kali user account would be perfect to use. However I want everyone to create a new user account using their student ID number, and full name so something like b00123456, Mark Cummins. 

>:warning: Obviously you should use you own student number in place of the demo ID I'm using

```bash
kali@kali:~$ sudo adduser b00123456
Adding user 'b00123456' ...
Adding new group 'b00123456' (1001) ...
Adding new user 'b00123456' (1001) with group 'b00123456' ...
Creating home directory '/home/b00123456' ...
Copying files from '/etc/skel' ...
New password: 
Retype new password: 
passwd: password updated successfully
Changing the user information for b00123456
Enter the new value, or press ENTER for the default
        Full Name []: Mark Cummins
        Room Number []: 
        Work Phone []: 
        Home Phone []: 
        Other []: 
Is the information correct? [Y/n] Y
```

This will create a new user and automatically creates a home directory. To verify if that has worked type: 

```bash
kali@kali:~$ ls /home/
b00123456 kali
```

And your newly created user should show up.

Now we need to add our new user to the Sudo’ers group. By adding the user to the sudo group, you are allowed to run commands that require root by putting the “sudo” command in front of it. Just think of it as “Do this command as root”, or simply remember “Superuser Do”.

```bash
kali@kali:~$ sudo usermod -aG sudo b00123456
```

Now we just have to set the user up for BASH. To do that, run:

```bash
kali@kali:~$sudo chsh -s /bin/bash b00123456
```

Now just log out of your Kali user account and log in with your new user.  

>:bulb: You'll find the logout option in the upper right corner. Always log in with your new user from now onwards. 

## 4. Customise Your Wallpaper

Ok definitely not an essential job on our list of tweaks but like the individual student IDs it will allow me view people's work easier if they don't all look the exact same. So again I'm going to insist people set their own background and try not to use any of the included default 
wallpapers, be creative.

Right click on your desktop and choose **Desktop Settings** to configure your wallpaper. 

> :bulb: You might want to search for a good wallpaper online first.


## Update and Upgrade

Our next step is to open up a terminal by clicking the icon on the top panel, then type **sudo apt update && sudo apt dist-upgrade -y**, this updates all the Kali repositories and then upgrades Kali and all its tools to the latest version. (Should take a while)

## Create a Snapshot

Now that we've set up our Kali image the way we want we should create a snapshot of this base install. If we end up messing up our install or just want a fresh install we can revert back to our snapshot at any stage. 



## Play Over The Wire

Overthewire is the place where you can practice and ramp up your basic Linux skills using your Linux VM for the first time. Overthewire.org is a great place to start your journey into Cyber Security because you need the commands used there on a daily basis.

You start with Bandit Level 0 and you will work your way all the way through until you reach Level 34. I highly recommend you don’t look up the straight solutions. Use your Google-Fu and start researching.

An example search would be: “How to find files on Linux”, or, “How to find certain lines of text on Linux”.

If you really get stuck and your brain is fried,  there are other websites out there that cover the whole thing. But again, I encourage you to try it on your own first!

Once you finish Bandit, you can go ahead and continue with any of the other challenges if you wish, they are all great.
