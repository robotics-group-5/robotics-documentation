# Setup the ROS2 Workspace

1. Open a terminal (should be in the home directory by default)

2. Create a directory called dev_ws to use as a ROS workspace

    `mkdir dev_ws` **(for the development machine)**

    `mkdir robot_ws` **(for the Raspberry Pi)**

3. Go into that and create a directory called src to put the packages into

    `cd dev_ws` OR `cd robot_ws`

    `mkdir src`

4. Go into that and clone our package from GitHub

    `cd src/`

    `git clone ssh://john@example.com/path/to/my-project.git`

5. Go back up to the workspace root and build it with colcon using the symlink-install setting.

    `cd ..`

    `colcon build --systemlink-install`

Congratulations, your package is built!