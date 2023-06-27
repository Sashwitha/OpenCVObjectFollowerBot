
# OpenCVObjectFollowerBot

This repository contains the code for an object-following robot using OpenCV. The robot is designed to track and follow a specific object in its surroundings using computer vision techniques provided by the OpenCV library.




## Features

Real-time object tracking: The robot utilizes OpenCV's object detection and tracking algorithms to locate and track a specified object in real-time.

Autonomous movement: Based on the object's position in the camera frame, the robot autonomously adjusts its movement to keep the object in the center of the frame.

User-friendly interface: The code provides a user-friendly interface that allows users to easily configure the object to be tracked, camera settings, and control the robot's behavior.


## Prerequisites 

ROS2-Humble

Gazebo (Simulation)

OpenCV (Object detection)

Slam Toolbox (Mapping)

Nav2 (Navigation)

## Installation

Installing OpenCV

```bash
  sudo apt install python3-opencv
```
```bash
  source install/setup.bash
```

Installing Slam Toolbox

```bash
  sudo apt install ros-humble-slam-toolbox
```
Installing Nav2

```bash
  sudo apt install ros-humble-navigation2 ros-humble-nav2-bringup 
```

```bash
   cd ~/ros2_ws
```
Spawning the robo in Gazebo
```bash
   ros2 launch articubot_one launch_sim.launch.py world:=/home/yashwitha/ros2_ws/src/articubot_one/worlds/project.world 
```
```bash
   rviz2
```
Localisation using slam toolbox

```bash
   ros2 launch articubot_one online_async_launch.py params_file:=./src/articubot_one/config/mapper_params_online_async.yaml use_sim_time:=true
```
Navigation
```bash
    ros2 launch nav2_bringup navigation_launch.py use_sim_time:=true
```
```bash
   add map, tf2 and robot_model in rviz2
```

```bash
   cd /path/articubot_one/launch
```
For moving the robot to the final pose
```bash
   python3 ./robot_navigator.py 
```
For going to the final pose position as specified in the code
```bash
   python3 ./navigator_sample2.py 
```

```bash
   cd ~/ros2_ws
```
Detection and following of the ball using OpenCV
```bash
   ros2 launch ball_tracker ball_tracker.launch.py params_file:=src/articubot_one/config/ball_tracker_params_example.yaml
```
Try running the navigator_sample2.py and ball tracker code simultaneously 


