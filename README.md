# ROS_Project

# Part 1

# udm_project_urdf

Contains the legged robot model - Une_Jambe.urdf

To launch the one leg on Rviz

```
roslaunch udm_project_urdf P1_visualize_urdf.launch
```

# udm_jambe_moveit_config

Makes use of the MoveIt Setup Assistant to configure one leg with MoveIt

To launch the one leg on Rviz

```
roslaunch udm_jambe_moveit_config demo.launch
```

# udm_project_control


## Cinematique directe

The robot hand moves its leg according to the joint values assigned 

- Terminal #1 - launch the demo to display the leg robot in RViz

```
roslaunch udm_jambe_moveit_config demo.launch
```

- Terminal #2 - Run the python file with rosrun

```
rosrun udm_project_control direct_cine_service.py
```

- Terminal #3 - Call the service

```
rosservice call /direct_cine_service "joint_goal1:
  data: 0.0
joint_goal2:
  data: 0.2
joint_goal3:
  data: 0.5
joint_goal4:
  data: 0.0
group:
  data: 'une_jambe'"
```

## Cinematique indirecte

The robot hand moves its leg according to the goal position assigned 

- Terminal #1 - launch the demo to display the leg robot in RViz

```
roslaunch udm_jambe_moveit_config demo.launch
```

- Terminal #2 - Run the python file with rosrun

```
rosrun udm_project_control indirect_cine_service.py
```

- Terminal #3 - Call the service

```
rosservice call /indirect_cine_service "pose:
orientation:
  w: 1
position:
  x: 0.3
position:
  y: 0.3
position:
  z: -0.1"
```

# Part 2 

## udm_project_urdf

URDF for the 4 legged robot - main_robot.urdf

```
roslaunch udm_project_urdf P2_visualize_urdf.launch
```
## moveleg_moveit_config

Contains the moveit config for the four legged robot

## Déplacer le robot en ligne droite, à gauche, à droite ou en arrière.

- Terminal #1 - launch the demo to display the hand robot in RViz

```
roslaunch moveleg_moveit_config demo.launch
```

- Terminal #2 - Launch the service

```
roslaunch udm_project_control move.launch 
```
The robot will move forward, right, backward and left.
