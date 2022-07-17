# AI task 1
#### First, I downloaded the virtual box.
##### Download Link [https://www.virtualbox.org/] 
#### Then I downloaded Ubuntu 20.04.4
##### Download Link [https://releases.ubuntu.com/20.04/]
##### Then after installing Ubuntu on the virtual box, I opened the terminal and I typed the following commands to install the (( Ros ))
##### I take the commands to install the Ros from the official site [http://wiki.ros.org/Installation/Ubuntu]
#### Commands to install the Ros
## 1- Installation
## 2- Setup your sources.list
~~~~
sudo sh -c 'echo "deb http://packages.ros.org/ros/ubuntu $(lsb_release -sc) main" > /etc/apt/sources.list.d/ros-latest.list'
~~~~~

## 3 - Set up your keys
~~~~~
sudo apt install curl # if you haven't already installed curl
curl -s https://raw.githubusercontent.com/ros/rosdistro/master/ros.asc | sudo apt-key add -
~~~~~

## 4- Installation
~~~~
sudo apt update
~~~~
## 5- Now pick how much of ROS you would like to install.
~~~~
sudo apt install ros-noetic-desktop-full
~~~~

## 6- Environment setup
~~~~~
source /opt/ros/noetic/setup.bash
echo "source /opt/ros/noetic/setup.bash" >> ~/.bashrc
source ~/.bashrc
~~~~~
## 7- Dependencies for building packages
~~~~
sudo apt install python3-rosdep python3-rosinstall python3-rosinstall-generator python3-wstool build-essential
~~~~
## 8- Initialize rosdep 
~~~~
sudo rosdep init
rosdep update
~~~~

# step 2
~~~~
sudo apt-get install ros-noetic-catkin
 
mkdir -p ~/catkin_ws/src
 
cd ~/catkin_ws/
 
catkin_make
 
cd ~/catkin_ws/src
 
git clone https://github.com/smart-methods/arduino_robot_arm.git 
 
cd ~/catkin_ws
 
rosdep install --from-paths src --ignore-src -r -y
 
sudo apt-get install ros-noetic-moveit
 
sudo apt-get install ros-noetic-joint-state-publisher ros-noetic-joint-state-publisher-gui
 
sudo apt-get install ros-noetic-gazebo-ros-control joint-state-publisher
 
sudo apt-get install ros-noetic-ros-controllers ros-noetic-ros-control
 
sudo nano ~/.bashrc
 
at the end of the (bashrc) file add the follwing line 
but change it to you name
 
source /home/badriah/catkin_ws/devel/setup.bash
 
source ~/.bashrc
 
roslaunch robot_arm_pkg check_motors.launch
~~~~
# Task execution picture
<div>
<img src="https://user-images.githubusercontent.com/108167855/179424309-5a5b2e8a-e408-43b5-93af-843b5362778c.png" width="350" height="200">
</div>
