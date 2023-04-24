## Install Colcon, the ROS2 Build Tool

ROS2 uses colcon as a build tool (and ament as the build system). When you only install the ROS2 core packages, colcon is not here, so install it manually.

`sudo apt install python3-colcon-common-extensions`

## Auto-completion for ROS2 command line tools

ROS2 comes with a lot of useful command line tools, and if you want to be able to use auto-completion for those tools, you’ll need to install The argcomplete Python module. First make sure you have pip3 installed.

`sudo apt install python3-pip`

`pip3 install argcomplete`