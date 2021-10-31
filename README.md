# Turtlebot3 Navigation and SLAM


## Table of Contents

- [Description](#description)
- [Getting Started](#getting-started)
- [Usage and Configuration Instructions](#usage-and-configuration-instructions)



## Description
The goal is to use the turtlebot to map an environment and then navigate within the map using slam_toolbox.<br>
The package contain 4 launchfiles and 1 node:

**explore** - A node that causes the robot to explore the environment autonomously while mapping the world.

**start_slam.launch** - Starts the turtlebot3 on gazebo (in the house environment), and drives the turtlebot3 using `turtlebot3_teleop.py` node throughout its workspace, while running `slam_toolbox`. After exploring the map, you can use the mapserver to save the map file.

**nav_stack.launch** - Uses `amcl` to localize your robot and the ROS navigation stack to allow the robot to move using the map created in the previous step.

**slam_stack.launch** - Runs all of the `nav-stack.launch` components, except instead of starting amcl and a pre-built map uses `slam_toolbox` to create the map while navigating.

**explore.launch** - Lets the robot use the `explore.py` node and `slam_toolbox` to autonomously map the environment.


## Getting Started

Create a workspace, clone the repo, and build the workspace:
```
mkdir -p ws/src && cd ws/src
git clone https://github.com/YaelBenShalom/Turtlebot3-Navigation-with-SLAM.git
cd ../..
catkin_make
source devel/setup.bash 
```


## Usage and Configuration Instructions

1. To launch the `start_slam.launch` launchfile on Gazebo and Rviz simulation, run:<br>
    `roslaunch Turtlebot3-Navigation-with-SLAM start_slam.launch`.

    - Explore the environment using the 2D pose estimation and 2D navigation goals in Rviz.
    - To save the explored map, run `rosrun map_server map_saver -f maps/map` from another terminal while the `start_slam.launch` launchfile is still running.

2. To launch the `nav_stack.launch` launchfile on Gazebo and Rviz simulation, run:<br>
    `roslaunch Turtlebot3-Navigation-with-SLAM nav_stack.launch`.

    - Move the robot by setting 2D navigation goals in Rviz.

    <p align="center">
        <img align="center" src="https://github.com/YaelBenShalom/Turtlebot3-Navigation-with-SLAM/blob/master/videos/nav_stack.gif">
    </p>


3. To launch the `slam_stack.launch` launchfile on Gazebo and Rviz simulation, run:<br>
    `roslaunch Turtlebot3-Navigation-with-SLAM slam_stack.launch`.

    - Explore the space by setting 2D navigation goals manually in rviz.

    <p align="center">
        <img align="center" src="https://github.com/YaelBenShalom/Turtlebot3-Navigation-with-SLAM/blob/master/videos/slam_stack.gif">
    </p>

4. To launch the `explore.launch` launchfile on Gazebo and Rviz simulation, run:<br>
    `roslaunch Turtlebot3-Navigation-with-SLAM explore.launch`.

    - Explore the space by randomly picking 2D navigation goals automatically in rviz.

    <p align="center">
        <img align="center" src="https://github.com/YaelBenShalom/Turtlebot3-Navigation-with-SLAM/blob/master/videos/explore.gif">
    </p>
    
    (This video speed is X10)

    - The generated map:

    <p align="center">
        <img align="center" src="https://github.com/YaelBenShalom/Turtlebot3-Navigation-with-SLAM/blob/master/videos/map.jpg">
    </p>
