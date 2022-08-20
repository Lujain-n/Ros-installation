# Ros-installation
Install Ros on windows 10 

1- we Download Virtual box from the link (https://www.virtualbox.org/wiki/Downloads )
2- Download Ubuntu 20.04 from the link ( https://releases.ubuntu.com/20.04/ )
3- Download Ros Noetic (https://wiki.ros.org/noetic/Installation/Ubuntu)

Download Ubuntu 20.04:
Open the virtual box 
click new to creat virtual machine 

1-fill the Name (write Ubuntu 20.04 the name of the version)
2- select how much of your hard disk your VM will use.
3- hard disk files type is VDI
4- storage on physical hard disk select Dynamically allocated 
5- set the maximum amount of memory your VM can access.

Ros Installing : 
If you install Ubuntu 20.04 the beast version of Ros is Ros noetic. 
At first open Ubuntu 20.04 then open new terminal then write the following codes: 
 1-Setup your sources.list : 

•	sudo sh -c 'echo "deb http://packages.ros.org/ros/ubuntu $(lsb_release -sc) main" > /etc/apt/sources.list.d/ros-latest.list'

2- Set up your keys

•	sudo apt install curl # if you haven't already installed curl
•	curl -s https://raw.githubusercontent.com/ros/rosdistro/master/ros.asc | sudo apt-key add -

3-Installations 
   First you need to up date your Debian package index by the code: 
   
•	sudo apt update

4- Then install Ros Desktop- full install :

sudo apt install ros-noetic-desktop-full

5- setup environment : 

echo "source /opt/ros/noetic/setup.bash" >> ~/.bashrc
source ~/.bashrc

6- To make sure that Ros package are install write (Roscore) if the following results appear that’s mean Ros install successfully:


Install Xubuntu 20.04 from this link (https://xubuntu.org/release/20-04/)


Install Ros 2 Foxy on Ubuntu 20.04 

1-setup locale 
Open new terminal then write locale if this appear that mean you have locale : 

If you don’t see an output line like the one above ,setup the locale : 

locale  # check for UTF-8

sudo apt update && sudo apt install locales
sudo locale-gen en_US en_US.UTF-8
sudo update-locale LC_ALL=en_US.UTF-8 LANG=en_US.UTF-8
export LANG=en_US.UTF-8

locale  # verify settings

2-setup sources 
make sure that the Ubuntu Universe repository is enabled by checking the output of this command. 

apt-cache policy | grep universe

The output  line :

500 http://us.archive.ubuntu.com/ubuntu focal/universe amd64 Packages
    release v=20.04,o=Ubuntu,a=focal,n=focal,l=Ubuntu,c=universe,b=amd64

If you don’t see an output line like the one above, then enable the Universe repository with these code: 

sudo apt install software-properties-common
sudo add-apt-repository universe

Now add the ROS 2 apt repository to your system: 

sudo apt update && sudo apt install curl gnupg2 lsb-release sudo curl -sSL https://raw.githubusercontent.com/ros/rosdistro/master/ros.key  -o /usr/share/keyrings/ros-archive-keyring.gpg

Then add the repository to your sources list.

echo "deb [arch=$(dpkg --print-architecture) signed-by=/usr/share/keyrings/ros-archive-keyring.gpg] http://packages.ros.org/ros2/ubuntu $(source /etc/os-release && echo $UBUNTU_CODENAME) main" | sudo tee /etc/apt/sources.list.d/ros2.list > /dev/null

Install Ros2 packages: 
Update your apt repository :

 sudo apt update
 
Install the Desktop Ros 2 : 

sudo apt install ros-foxy-desktop


