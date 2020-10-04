# RI project part 2
This repo contains the packages of the second part of the project.

# part_two_urdf
This package the urdf of one of the quadruped robot as well as a launch file to visualize the robot.

# udm_project_moveitconfig
This package was generated with moveit.

# udm_project_control
This package contains the nodes, services and launch files needed to move the robot straight, right, left and back.

# Installation
To install this node you have to clone it in the src folder of your catkin workspace (catkin_ws).

`` ``
cd catkin_ws / src
git clone https://github.com/ddomah/Robotique-Industrielle
catkin build
cd ..
source devel / setup.bash
`` ``
# Execution
# Visualize the leg
To view, you must execute the following code in the terminal of your workspace:

`` ``
source devel / setup.bash
roslaunch part_two_urdf simulate.launch
`` ``
# Control the leg using direct kinematics

In the first terminal of your catkin workspace:
`` ``
source devel / setup.bash
roslaunch udm_project_moveitconfig demo.launch
`` ``

In the second terminal of your catkin workspace:
`` ``
source devel / setup.bash
roslaunch udm_project_control control.launch
`` ``

In the third terminal of your catkin workspace:
`` ``
source devel / setup.bash
rosservice call / control "movement:
 data: 'front' "
`` ``
NB: You can choose the following values: 'front', 'right', 'left', 'back'.
