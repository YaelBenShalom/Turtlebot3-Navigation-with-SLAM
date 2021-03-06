# MECH_ENG_495 - Homework 4
GitHub repository - `https://github.com/YaelBenShalom/Turtlebot3-Navigation-with-SLAM`

## Overview
The goal is to use the turtlebot to map an environment and then navigate within the map using slam_toolbox.

The package contain 4 launchfiles and 1 node:

**explore** - A node that causes the robot to explore the environment autonomously while mapping the world.

**start_slam.launch** - Starts the `turtlebot3` on gazebo (in the house environment), and drives the turtlebot3 using `turtlebot3_teleop` node throughout its workspace, while running `slam_toolbox`. After exploring the map, you can use the mapserver to save the map file.

**nav_stack.launch** - Uses `amcl` to localize your robot and the ROS navigation stack to allow the robot to move using the map created in the previous step.

**slam_stack.launch** - Runs all of the `nav-stack.launch` components, except instead of starting amcl and a pre-built map uses `slam_toolbox` to create the map while navigating.

**explore.launch** - Lets the robot use the `explore` node and `slam_toolbox` to autonomously map the environment.


## Usage and Configuration instructions
1. To launch the `start_slam` launchfile on Gazebo and Rviz simulation, run `roslaunch homework4 start_slam.launch`.

    - Explore the environment using the 2D pose estimation and 2D navigation goals in Rviz.

    - To save the explored map, run `rosrun map_server map_saver -f maps/map` from another terminal while the `start_slam` launchfile is still running.

2. To launch the `nav_stack` launchfile on Gazebo and Rviz simulation, run `roslaunch homework4 nav_stack.launch`.

     - Move the robot by setting 2D navigation goals in Rviz.

    ![The robot navigates to a 2D navigation goal in Rviz](https://github.com/YaelBenShalom/Turtlebot3-Navigation-with-SLAM/blob/master/videos/nav_stack.gif)


3. To launch the `slam_stack` launchfile on Gazebo and Rviz simulation, run `roslaunch homework4 slam_stack.launch`.

     - Explore the space by setting 2D navigation goals manually in rviz.

    ![The robot navigates to a unknown 2D navigation goal in Rviz](https://github.com/YaelBenShalom/Turtlebot3-Navigation-with-SLAM/blob/master/videos/slam_stack.gif)

4. To launch the `explore` launchfile on Gazebo and Rviz simulation, run `roslaunch homework4 explore.launch`.

     - Explore the space by randomly picking 2D navigation goals automatically in rviz.

    ![The robot navigates to random 2D navigation goals in Rviz](https://github.com/YaelBenShalom/Turtlebot3-Navigation-with-SLAM/blob/master/videos/explore.gif)
    
    (This video speed is X10)

    - The generated map:

    ![The generated map](https://github.com/YaelBenShalom/Turtlebot3-Navigation-with-SLAM/blob/master/videos/map.jpg)
