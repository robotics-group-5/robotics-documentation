# Install ROS2 Humble on Ubuntu 22.04

TODO

## Set locale
Make sure you have a locale which supports UTF-8. We test with the following settings. However, it should be fine if you’re using a different UTF-8 supported locale.

`locale`  # check for UTF-8

`sudo apt update && sudo apt install locales`

`sudo locale-gen en_US en_US.UTF-8`

`sudo update-locale LC_ALL=en_US.UTF-8 LANG=en_US.UTF-8`

`export LANG=en_US.UTF-8`

`locale`  # verify settings

## Setup sources

You will need to add the ROS 2 apt repository to your system.

First ensure that the [Ubuntu Universe repository](https://help.ubuntu.com/community/Repositories/Ubuntu) is enabled.

`sudo apt install software-properties-common`

`sudo add-apt-repository universe`

Now add the ROS 2 GPG key with apt.

`sudo apt update && sudo apt install curl -y`

`sudo curl -sSL https://raw.githubusercontent.com/ros/rosdistro/master/ros.key -o /usr/share/keyrings/ros-archive-keyring.gpg`

Then add the repository to your sources list.

`echo "deb [arch=$(dpkg --print-architecture) signed-by=/usr/share/keyrings/ros-archive-keyring.gpg] http://packages.ros.org/ros2/ubuntu $(. /etc/os-release && echo $UBUNTU_CODENAME) main" | sudo tee /etc/apt/sources.list.d/ros2.list > /dev/null`

## Install ROS 2 Packages

Update your apt repository caches after setting up the repositories.

`sudo apt update`

ROS 2 packages are built on frequently updated Ubuntu systems. It is always recommended that you ensure your system is up to date before installing new packages.

`sudo apt upgrade`

Desktop Install (Recommended): ROS, RViz, demos, tutorials. **Use this for the install on your development pc**

`sudo apt install ros-humble-desktop`

ROS-Base Install (Bare Bones): Communication libraries, message packages, command line tools. No GUI tools. **Use this for the install on the Raspberry Pi, since we don't need the GUI**

`sudo apt install ros-humble-ros-base`

## Setup your environment

In order to actually use ROS2, you’ll need to setup your environment every time you open a new session (terminal). To source your ROS2 installation in your environment, run `source /opt/ros/humble/setup.bash`

And because it won’t be that practical to do this for every new session you open, add this line to your bashrc.

`echo "source /opt/ros/humble/setup.bash" >> ~/.bashrc`

So, from now on, every time you open a terminal, your bashrc will be executed and your environment will be ready for ROS2.