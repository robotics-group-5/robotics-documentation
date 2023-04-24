# Install ROS2 Humble on Ubuntu 22.04

TODO

## Set locale
Make sure you have a locale which supports UTF-8. We test with the following settings. However, it should be fine if you’re using a different UTF-8 supported locale.

`locale  # check for UTF-8

sudo apt update && sudo apt install locales
sudo locale-gen en_US en_US.UTF-8
sudo update-locale LC_ALL=en_US.UTF-8 LANG=en_US.UTF-8
export LANG=en_US.UTF-8

locale  # verify settings`