Final-Assignment
================================

Final assignment of the Research Track 1 course, development of a software architecture for the control of a mobile robot.
It's a Python code to control the movement of a robot inside a the given map which resembles a box with rooms. The user must choose a modality of control of the robot:
* autonomously reach a x,y coordinate inserted by the user.
* let the user drive the robot with the keyboard.
* let the user drive the robot assisting them to avoid collisions.

Installing and running
----------------------
Download (or even better, fork) the repository from: [CarmineD8/final_assignment](https://github.com/CarmineD8/final_assignment.git) and the [slam_gmapping](https://github.com/CarmineD8/slam_gmapping.git) package, having care to switch on the `noetic` branch.
The ros navigation stack
```bash
Apt-get install ros-<your_ros_distro>-navigation
```
is needed

After you download and build the workspace, make sure to make all the .py files in the scripts folder as executables:
```bash
chmod +x <name_pythonSript.py>
```

then run in three different shells the three launcher needed:
```bash
$ roslaunch final_assignment simulation_gmapping.launch
$ roslaunch final_assignment move_base.launch
$ roslaunch assignment_three launcher.launch
```

the first two launch files are launching a robotic simulation on Gazebo and Rviz, the last launch file is the one that executes the user interface with the explenation of the actions in the code.

Structure
-----------------------------
The logic of the code and how those three nodes communicate is written in the [flowchart](Final_flowchar.jpg).
The software rely on the move_baseand gmapping packages for localizing the robot and plan the motion.

### Mode 1 -automatic reach- ###
The action of the move_base package is used, given a goal in the world, will attempt to reach it with a mobile base.
`manage_input(request)` : function to manage the user choice of mode 1. Sets the target and waits for the result.
`directions_server()` :
    #node description
