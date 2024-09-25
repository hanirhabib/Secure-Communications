# Setting up VSCode11

You'll be glad to hear we're almost done with our lab environment setup. The final piece of the jigsaw is an IDE so we can do some coding. Again any IDE or text editor would probably be enough for the few bits of coding we're doing but I think using a feature rich IDE such as VSCode offers plenty of advantages.

We'll be using VSCode for our coding (Python 3) but we can also use it to connect to our Github accounts. There are  plugins available for pretty much every feature you could dream of, so we can use VSCode for much more than just our coding.
___

## Lab Contents

1. Installing VSCode on Kali
2. Adding a college folder
3. Adding some plugins
4. Adding some Python packages
5. Connecting VSCode to our Github account
6. Our sample Github Workflow


___

### 1. Installing VSCode on Kali

On our Kali VM open a web browser and goto the Visual studio download page [https://code.visualstudio.com/download](https://code.visualstudio.com/download) and download the linux .deb file.

Once downloaded open a terminal and navigate to where ever you downloaded the file and install VSCode.

```bash
kali@kali:~$ cd Downloads/
kali@kali:~/Downloads$ ls
code_1.49.2-1600965325_amd64.deb
kali@kali:~/Downloads$ sudo apt install ./code_1.49.2-1600965325_amd64.deb
```

> :bulb: once installed you can open VSCode from the command line by typing **code**

### 2. Adding a college folder

Once installed open VSCode and goto File/ Open Folder, and create and add a college folder or similar for us to keep all our secure communications lab work.

> :bulb: if you did all the steps in the earlier Github lab section you likely already have this setup.


### 3. Adding some plugins

OK, next we want to add some plugins. VSCode's plugins are the strength of the app and there are some amazing plugins, so feel free to add your own plugins an themes etc. As a minimum I'm going to suggest you add the following plugins, search the marketplace and add the following:

- Python (Microsoft)
- AREPL for python
- Code Spell Checker
- Markdown Preview Github Styling
- Markdown Emoji
- Whatever else takes your fancy...

> :bulb: Click the small cubes icon on the left hand side of VSCode to see plugins) 

### 4. Adding some Python packages

Our Kali VM has Python (versions 2 & 3) installed by default, I suggest you just use python 3, (python 2 is depreciated). We'll still want to add some extra packages to help us with our crypto programming. Let's use the helpful terminal window within VSCode, and type the following commands.

```bash
kali@kali:~/Documents/College$ python3 --version
Python 3.8.5
kali@kali:~/Documents/College$ pip3 install pycryptodome
Collecting pycryptodome
...
Successfully installed pycryptodome-3.9.8
```

That's it with python for now.

### 5. Connecting VSCode to our Github account

The last bit of configuring we want to complete is connecting our Github account to VSCode so we can easily interact with github directly from VSCode.

So start by adding a new random folder to VSCode, then click on the version control icon on the left hand panel. (It looks like three connected circles) Then while online click on the highlighted *Publish to Github** link, VSCode will attempt to connect to you github account and ask you for some permissions. but once connected you'll be able to create new repos on Github and easily push and pull content.

### 6. Our sample Github Workflow

To see all of this is action the easiest way is to check out the small video I've prepared on the Moodle page that will step you though a simple sample workflow. If you're happy to can follow al the steps try it yourself a couple of times.
