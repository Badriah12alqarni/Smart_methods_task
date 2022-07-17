# AI task 2
#### First, I downloaded the virtual box.
##### Download Link [https://www.virtualbox.org/] 
#### Then I downloaded XUbuntu 20.04.4
##### Download Link [https://xubuntu.org/download/]
##### Then after installing XUbuntu on the virtual box, I opened the terminal and I typed the following commands to install the (( Ros 2 ))
##### I take the commands to install the Ros 2 from the official site [https://docs.ros.org/en/foxy/Installation/Ubuntu-Install-Debians.html]
#### Commands to install the Ros
## 1- Set locale
~~~~
locale  # check for UTF-8

sudo apt update && sudo apt install locales
sudo locale-gen en_US en_US.UTF-8
sudo update-locale LC_ALL=en_US.UTF-8 LANG=en_US.UTF-8
export LANG=en_US.UTF-8

locale  # verify settings
~~~~
## 2- Setup Sources
~~~~
apt-cache policy | grep universe    
~~~~
This should output a line like the one below
~~~~
500 http://us.archive.ubuntu.com/ubuntu focal/universe amd64 Packages
    release v=20.04,o=Ubuntu,a=focal,n=focal,l=Ubuntu,c=universe,b=amd64 
~~~~
If you don’t see an output line like the one above, then enable the Universe repository with these instructions.
~~~~
sudo apt install software-properties-common
sudo add-apt-repository universe
~~~~
Now add the ROS 2 apt repository to your system.
~~~~
sudo apt update && sudo apt install curl gnupg2 lsb-release
sudo curl -sSL https://raw.githubusercontent.com/ros/rosdistro/master/ros.key  -o /usr/share/keyrings/ros-archive-keyring.gpg
~~~~
Then add the repository to your sources list.
~~~~
echo "deb [arch=$(dpkg --print-architecture) signed-by=/usr/share/keyrings/ros-archive-keyring.gpg] http://packages.ros.org/ros2/ubuntu $(source /etc/os-release && echo $UBUNTU_CODENAME) main" | sudo tee /etc/apt/sources.list.d/ros2.list > /dev/null
~~~~
## Install ROS 2 packages

Update your apt repository caches after setting up the repositories.
~~~~
sudo apt update
~~~~

ROS 2 packages are built on frequently updated Ubuntu systems. It is always recommended that you ensure your system is up to date before installing new packages.
~~~~
sudo apt upgrade
~~~~
Desktop Install (Recommended): ROS, RViz, demos, tutorials.
~~~~
sudo apt install ros-foxy-desktop
~~~~
## Environment setup
~~~~
source /opt/ros/foxy/setup.bash
~~~~



