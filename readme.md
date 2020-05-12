# Windows Dev Environment

While we **strongly** recommend students use Macs for our training programs, we acknowledge that there are a number of limitations that may prevent a student from using/having access to a Mac. 

While Apple is the standard for developers, Microsoft has taken strides to improve the experience of developing on a Windows machine. First and foremost among these steps is their support for  **Windows Subsystem for Linux**.


In this repo are instructions for setting up:

1. Windows Subsystem for Linux
2. Git for Windows
3. Git for WSL
4. Node and NPM
5. Docker
6. 

## Getting Set Up

### 1. Windows Subsystem for Linux (WSL)

- Download Ubuntu from the Microsoft Store App on your Windows machine or follow this link: [https://www.microsoft.com/en-us/p/ubuntu/9nblggh4msv6](https://www.microsoft.com/en-us/p/ubuntu/9nblggh4msv6)

- WSL is an optional feature on Windows, it disabled by default so we'll need to enable it.

1. Open your start menu and search for "Windows Features"
2. Select "turn windows features on or off"
3. Scroll down and check the box labeled "Windows Subsystem for Linux"
4. Hit OK - It may take a minute because we are installing the Linux File System on our OS.
5. Restart

	
> If you have issues with the above steps you can still enable WSL through a different method.
> 	
> - Open Powershell as an administrator
>		- Start -> Search for "Powershell" -> Right click, Run as Administrator
> - Execute the following command by pasting it into Powershell:
>	
> `Enable-WindowsOptionalFeature -Online -FeatureName Microsoft-Windows-Subsystem-Linux`
>		
>	
>	- Once it finishes executing you'll be give an option to **Restart** your machine, which you will need to do.

- When your computer reboots open up the Ubuntu app that we downloaded earlier by opening your start menu and searching "Ubuntu" or by checking the top left area of your start menu where recently installed apps are located.
- A terminal style window should open up with the words "Installing..."
- When this finishes congratulations! You can now run Bash from the start menu, Powershell, the command prompt, or whatever terminal emulator you like!

### 2. Git

Depending on your needs you may need to set up Git twice: once for your Windows CMD and once for your Linux WSL shell. If you plan to do all your work through the WSL then **skip to Installing Git for WSL**.

#### Installing Git for Windows

1. Download the Git for Windows installer from [https://git-scm.com/download/win](https://git-scm.com/download/win)
2. Run the installer and follow the instructions.

> You'll be given a lot of options as you progress through the installer. We suggest sticking with the **default options**.


#### Installing Git for WSL

- To download and install Git open Ubuntu and execute the following command `sudo apt install git`

You will need to enter your password whenever you use the `sudo` command. 

> The `sudo` command allows you to run programs with the security priveledges of another user, by default the superuser. It stands for "superuser do".

#### Configuring Git

You may also want to supply some config information for Git to use. 

```
git config --global user.name "Ash Coca"
git config --global user.email ash.coca@galvanize.com
```

> This is an optional step, but will make things a little faster when you're pushing and pulling from Github.


### 3. Node

- Install cURL (a tool used for downloading content from the internet in the command-line) with: `sudo apt-get install curl`

- Next we'll want to install NVM (Node Version Manager) This utility will allow you to manage multiple versions of node should you need to in the future. Execute this line:
 
	```curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.35.2/install.sh | bash```

- To verify installation, enter: `nvm -v` ...this should return 'nvm', if you receive 'command not found' or no response at all, **close your current terminal**, reopen it, and try again.

Now we're ready to install Node!

- Install the latest stable LTS release of Node.js (recommended): `nvm install --lts`

> You can optionally installing a specific version of node with `nvm install <version>` or the current version of node with `nvm install node`

 - Verify your install by entering `node -v`
 - We'll also want to verify our install of NPM (Node Package Manager - included with node) with `npm -v`
 
> If you installed multiple versions of node using NVM, you can view these installs with `nvm ls`
>
>  You can also use `which node` and `which npm` to see the path used for the default versions of these tools.
>
>To change the version of Node.js you would like to use for a project, create a new project directory `mkdir NodeTest`, and enter the directory `cd NodeTest`, then enter `nvm use node` to switch to the Current version, or `nvm use --lts` to switch to the LTS version. You can also use the specific number for any additional versions you've installed, like `nvm use v8.2.1`. (To list all of the versions of Node.js available, use the command: `nvm ls-remote`). 

## Additional Config Options

## Common Issues