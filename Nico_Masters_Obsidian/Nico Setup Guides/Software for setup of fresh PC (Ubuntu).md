
# VS code
1. Open Ubuntu Software App
2. Download and install code (VS Code)
3. Sign in using GitHub
4. VSCode should automatically install all necessary extensions
5. Setup Git in VSCode
	 - includes initializing  and verifying correct username and user email
```Shell
sudo apt update
sudo apt upgrade
sudo apt install git
git config --global user.name "NicoEpler"
git config --global user.email "2390712@sun.ac.za"
git config --global --list
```
6. Clone necessary Repos from Git

# Obsidian
- download snap file from [Obsidian](https://obsidian.md/download)
```bash
cd Downloads
snap install obsidian_1.5.8_amd64.snap --dangerous --classic
```
- Open folder as vault, to access this file

# Chrome
```bash
wget https://dl.google.com/linux/direct/google-chrome-stable_current_amd64.deb
sudo dpkg -i google-chrome-stable_current_amd64.deb
sudo apt install -f
```

# Terminator
```bash
sudo apt update
sudo apt upgrade 
sudo apt install terminator
```

# Python
```bash
sudo apt install python3
sudo apt install python3-pip
sudo apt install python3-colcon-common-extensions
```

# Latex
```bash
sudo apt update
sudo apt upgrade
sudo apt install texlive-full
```

[[Useful Latex Stuff-NicoE]] for shortcuts in latex







# Other installations...............
# ROS2 (Humble)
```bash
locale  # check for UTF-8

sudo apt update && sudo apt install locales
sudo locale-gen en_US en_US.UTF-8
sudo update-locale LC_ALL=en_US.UTF-8 LANG=en_US.UTF-8
export LANG=en_US.UTF-8

locale  # verify settings

sudo apt install software-properties-common
sudo add-apt-repository universe

sudo apt update && sudo apt install curl -y
sudo curl -sSL https://raw.githubusercontent.com/ros/rosdistro/master/ros.key -o /usr/share/keyrings/ros-archive-keyring.gpg

echo "deb [arch=$(dpkg --print-architecture) signed-by=/usr/share/keyrings/ros-archive-keyring.gpg] http://packages.ros.org/ros2/ubuntu $(. /etc/os-release && echo $UBUNTU_CODENAME) main" | sudo tee /etc/apt/sources.list.d/ros2.list > /dev/null

sudo apt update
sudo apt upgrade

sudo apt install ros-humble-desktop

sudo apt install ros-humble-ros-base

sudo apt install ros-dev-tools

sudo apt install python3-colcon-common-extensions

gedit ~/.bashrc
```
add the following to the end of the `~/.bashrc` script:
```bash
source /opt/ros/humble/setup.bash
source /usr/share/colcon_argcomplete/hook/colcon-argcomplete.bash
```
[[ROS2 commands]] 


# Slack
```bash
sudo snap install slack
```


# Docker
```bash
for pkg in docker.io docker-doc docker-compose docker-compose-v2 podman-docker containerd runc; do sudo apt-get remove $pkg; done

# Add Docker's official GPG key:
sudo apt-get update
sudo apt-get install ca-certificates curl
sudo install -m 0755 -d /etc/apt/keyrings
sudo curl -fsSL https://download.docker.com/linux/ubuntu/gpg -o /etc/apt/keyrings/docker.asc
sudo chmod a+r /etc/apt/keyrings/docker.asc

# Add the repository to Apt sources:
echo \
  "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.asc] https://download.docker.com/linux/ubuntu \
  $(. /etc/os-release && echo "$VERSION_CODENAME") stable" | \
  sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
sudo apt-get update
```
## Docker Compose
```bash
sudo apt install gnome-terminal
sudo apt-get update
cd Downloads
sudo apt-get install ./docker-desktop-4.28.0-amd64.deb

systemctl --user start docker-desktop

docker compose version
docker --version
docker version
```


