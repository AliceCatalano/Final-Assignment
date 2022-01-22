# Final-Assignment
================================

Final assignment of the Research Track 1 course. It's a Puthon code to controll the movement of a robot inside a the given map which resembles a box with rooms. The user must choose a modality of control of the robot:
* automatic reach of a point which coordinates are given by the user.
* full driving experience through keyboard command.
* driving experience with cruch control.

Installing and running
----------------------
Download (or even better, fork) the repository from: [CarmineD8/final_assignment](https://github.com/CarmineD8/final_assignment.git), having care to switch on the `noetic` branch.

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

the first two launch files are for Gazebo and Rviz for launch a robotic simulation

## Structure
-----------------------------
There ar
The logic of the code and how those three nodes communicate is written in the [flowchart](Flowchart.jpg)

### Controller ###
