# AUBO I5 Robot

This code is Based on https://github.com/AuboRobot/aubo_robot, it was applied to develop a demo for car washing robot where there is a x-y gantry robot near the top of a room and aubo i5 robot is mount below. 

### Verfied Features
1. control i5 and x-y gantry together with a ip address 
2. add co-simulation of x-y gantry robot with aubo i5 robot mounted on it  (new URDF model)
3. some bug fix for the orignal code 

### MoveIt! with a simulated robot
---

You can use MoveIt! to control the simulated robot like ***RVIZ*** ,***Gazebo*** or ***VREP*** environment. If you want to simulate the robot in RVIZ:

* First set up the MoveIt nodes to allow motion planning with 8 axis (x-y gantry + aubo i5) and run:

**rviz**
```  
        1.roslaunch aubo_i5_moveit_config moveit_planning_execution.launch robot_ip:=127.0.0.1  
```

**gazebo**  
```
        2.roslaunch aubo_gazebo aubo_<robot_name>_gazebo_control.launch
```
**you should install some package when you use aubo model in gazebo** [here](https://github.com/AuboRobot/aubo_robot/blob/master/aubo_gazebo/README.md)

* Then select `"Interact"` and move the end-effector to a new goal.

* In  `"Motion Planning"` -> `"Plan and Execute"` to send trajectory to the sim robot

* Exit RViz and Ctrl-C the demo.launch window

### Usage with real robot
---
* To bring up the real robot, run:

```
roslaunch aubo_i5_moveit_config moveit_planning_execution.launch sim:=false robot_ip:=<192.168.***.***>
```


### Demos and videos 

[![Real Robot Control] <img src="https://www.robots.ch/img/AUBO-i5.jpg" width="50%" height="50%">](https://www.youtube.com/watch?v=G6jAK9aeGHo&list=PLgLUD9HvNvmeXefMBWNDqegE-5NEDRRUW&index=2)

[![Simulation]](simulation.mp4)



