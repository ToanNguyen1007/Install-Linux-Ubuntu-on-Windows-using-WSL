# Install-Linux-Ubuntu-on-Windows-using-WSL
Step 1: Enable WSL
1. Opening Windows Powershell Terminal

<img width="747" height="714" alt="1" src="https://github.com/user-attachments/assets/9e629c44-6c2d-4d29-9829-da18405390d4" />

Run the WSL Installation Command:

```wsl --install```
It may ask you to choose a username and password
Restart Your Computer:
After the installation completes, you may need to restart your computer

Step 2: Install Ubuntu
Open Microsoft Store:
After restarting, open the Microsoft Store from the Start menu.

Search for Ubuntu:
In the Store, type "Ubuntu" in the search bar. You’ll see various versions like Ubuntu 20.04 LTS, Ubuntu 22.04 LTS, etc

Select and Install:
Click on the version you want to install, then click the Get or Install button

Step 3: Set Up Ubuntu
Launch Ubuntu:
Once installed, you can launch it directly from the Microsoft Store or by searching for "Ubuntu" in the Start menu
The first time you launch Ubuntu, it will take a moment to set up. After that, you will be prompted to create a new user account and password
Step 4: Install and Update Packages (aka Drivers)
Update and Upgrade default Packages
```sudo apt update

sudo apt upgrade```
Install more important packages
```sudo apt install curl iptables build-essential git wget lz4 jq make gcc nano automake autoconf tmux htop nvme-cli pkg-config libssl-dev libleveldb-dev tar clang bsdmainutils ncdu unzip libleveldb-dev  -y```
Install Docker
```sudo apt update -y && sudo apt upgrade -y
for pkg in docker.io docker-doc docker-compose podman-docker containerd runc; do sudo apt-get remove $pkg; done

sudo apt-get update
sudo apt-get install ca-certificates curl gnupg
sudo install -m 0755 -d /etc/apt/keyrings
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /etc/apt/keyrings/docker.gpg
sudo chmod a+r /etc/apt/keyrings/docker.gpg

echo \
  "deb [arch="$(dpkg --print-architecture)" signed-by=/etc/apt/keyrings/docker.gpg] https://download.docker.com/linux/ubuntu \
  "$(. /etc/os-release && echo "$VERSION_CODENAME")" stable" | \
  sudo tee /etc/apt/sources.list.d/docker.list > /dev/null

sudo apt update -y && sudo apt upgrade -y

sudo apt-get install docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin

# Docker version
docker --version```

Optional: To install more packages you can check my recent Linux guide

**Optional: Change user**
There are 2 ways to login to ubuntu: 1. You are root (administrator with full permissions), or 2. you are an specific user with specific permissions

You see by entering whoami, I am logged in as user:mirana

<img width="378" height="122" alt="2" src="https://github.com/user-attachments/assets/7d324fa9-2974-4ed9-87e5-6f634b818cca" />


If you want to login with root (full permissions):

```sudo su```
<img width="418" height="140" alt="3" src="https://github.com/user-attachments/assets/2d2fab34-97ef-4ed0-8d46-d5d4f022cdaf" />


Now you see I am as root user, but in mirana user main directory
I need to type cd to move to the main directory of root
To login to a specific user again, Enter this command: su - username

Access Ubuntu directories in Windows explorer
To go to your Ubuntu directory using Windows explorer, Enter this in Windows Explorer Addressbar

```\\wsl$```
home: main directory of your specific user
root: main directory of your root user
<img width="766" height="585" alt="4" src="https://github.com/user-attachments/assets/3dadd317-2c17-43a1-b553-f127bff1c89e" />

If you don't have access to root directory, Enter this command in terminal sudo chmod 755 /root
