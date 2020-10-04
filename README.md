# Robotique-Industrielle
MIAR Semestre 2 - Module Robotique Industrielle - Projet ROS

PART ONE

ROBOTIQUE_INDUSTRIELLE_P1

# RI project part 1
This repo contains the packages of the first part of the project.

# part_one_urdf
This package the urdf of a robot leg as well as a launch file to visualize the leg.

# udm_project_moveitconfig
This package was generated with moveit

# udm_project_control
This package contains the nodes, services and launch files necessary to control the leg through direct or reverse kinematics

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
roslaunch part_one_urdf simulate.launch
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
roslaunch udm_project_control direct.launch
`` ``

In the third terminal of your catkin workspace:
`` ``
source devel / setup.bash
rosservice call / direct_kin_service_legmr "joint1:
 data: -0.4
joint2:
 data: -0.4
joint3:
 data: 0.2
joint4:
 data: -0.3 "
`` ``
NB: You can choose other value.

# Control the leg using reverse kinematics

In the first terminal of your catkin workspace:
`` ``
source devel / setup.bash
roslaunch udm_project_moveitconfig demo.launch
`` ``

In the second terminal of your catkin workspace:
`` ``
source devel / setup.bash
roslaunch udm_project_control indirect.launch
`` ``

In the third terminal of your catkin workspace:
`` ``
source devel / setup.bash
rosservice call / indirect_kin_service_legmr "pose:
 orientation:
  w: 1
 position:
  x: 0.4
 position:
  y: 0.4
 position:
  z: -0.2 "
`` ``
NB: You can choose other value.


PART TWO

ROBOTIQUE_INDUSTRIELLE_P2
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
