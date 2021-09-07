cmake_minimum_required(VERSION 3.0.2)
project(turtlebot_navigation_and_mapping)

## Find catkin macros and libraries
find_package(catkin
  REQUIRED
  COMPONENTS
  turtlesim
)

###################################
## catkin specific configuration ##
###################################

## The catkin_package macro generates cmake config files for your package
## Declare things to be passed to dependent projects
catkin_package(
  CATKIN_DEPENDS
  turtlesim
)

#############
## Install ##
#############

## Mark executable scripts (Python etc.) for installation
## in contrast to setup.py, you can choose the destination
catkin_install_python(PROGRAMS
  nodes/explore.py
  DESTINATION ${CATKIN_PACKAGE_BIN_DESTINATION}
)

# Mark other files for installation (e.g. launch and bag files, etc.)
install(
  FILES
  rviz/explore.rviz
  DESTINATION ${CATKIN_PACKAGE_SHARE_DESTINATION}
)
