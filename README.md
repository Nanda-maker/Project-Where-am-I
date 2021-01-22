# Project-Where-am-I
Use the Adaptive Monte Carlo Localization Algorithm in ROS to estimate our Robot!
### Description
This repo has reference to the project **Where Am I** of the [Robotics Software Engineer Nanodegree program](https://www.udacity.com/course/robotics-software-engineer--nd209) offered by [Udacity](https://www.udacity.com/). This project focuses on the localisation of a robot using AMCL algorithm, in a gazebo-simulated mapped environment.
Create a ROS package that launches a custom robot model in a custom Gazebo world.
Utilize the ROS AMCL package and the Tele-Operation / Navigation Stack to localize the robot.
Explore, add, and tune specific parameters corresponding to each package to achieve the best possible localization results.
### Installation of some ROS packages
You could install them as shown below:
```sh
$ sudo apt-get install ros-kinetic-navigation
$ sudo apt-get install ros-kinetic-map-server
$ sudo apt-get install ros-kinetic-move-base
$ sudo apt-get install ros-kinetic-amcl
```
Perhaps update your system
```sh
$ sudo apt-get update && sudo apt-get upgrade -y
```
### Building the Project
1. Clone this repository into src folder of the workspace.
```sh
$ cd /home/workspace/catkin_ws/src
$cd ..
```
2. Build the project using the following commands:
```sh
$ cd /home/workspace/catkin_ws
$ catkin_make
$ source devel/setup.bash
```
3. Execute the project using the following commands in separate terminal of same directory(cd /home/workspace/catkin_ws):
```sh
$ roslaunch my_robot world.launch 
$ roslaunch myamcl amcl.launch
```
### Rviz Configuration
```sh
- Select: Global Options-> Fixed Frame-> Map

- Add Robot Model.

- Add Camera. Then Select Image Topic: /camera/rgb/image_raw.

- Add LaserScan. Then Select Image Topic: /scan.

- Add Maps. Then Select Image Topic: /map. Check other maps such as /move_base/local_costmap/costmap /move_base/global_costmap/costmap

- Add PoseArrow. Then Select Topic: /pointcloud.
```
### Testing
You have two options to control your robot while it localize itself here:
-	Send navigation goal via RViz
-	Send move command via teleop package. Run this command: 
```sh 
$ teleop_twist_keyboard teleop_twist_keyboard.py 
```
Navigate your robot, observe its performance and tune your parameters for AMCL! 
### Screenshot of the Project
![](https://github.com/Nanda-maker/Project-Where-am-I/blob/master/ScreenShotRobot.PNG)
