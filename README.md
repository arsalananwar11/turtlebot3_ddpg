# Autonomous Robot Navigation Using DRL

Using DRL, the goal is to train the Turtlebot3 Waffle Pi to reach a given destination by taking the optimal path and avoiding both the static and dynamic obstacles.  

- https://github.com/ROBOTIS-GIT/turtlebot3_machine_learning

## Libraries

[Pytorch]

## ROS 
Packages used:
- https://github.com/ROBOTIS-GIT/turtlebot3
- https://github.com/ROBOTIS-GIT/turtlebot3_msgs
- https://github.com/ROBOTIS-GIT/turtlebot3_simulations

```
cd ~/catkin_ws/src/
git clone {link_git}
cd ~/catkin_ws && catkin_make
```

To install my package you will do the same from above.

## Set State

In: turtlebot3/turtlebot3_description/urdf/turtlebot3_waffle_pi.gazebo.xacro.

```
<xacro:arg name="laser_visual" default="false"/>   # Visualization of LDS. If you want to see LDS, set to `true`
```
And
```
<scan>
  <horizontal>
    <samples>360</samples>            # The number of sample. Modify it to 36 to take one sample from each direction
    <resolution>1</resolution>
    <min_angle>0.0</min_angle>
    <max_angle>6.28319</max_angle>
  </horizontal>
</scan>
```

## Run Code

To simulate the environment:
```
roslaunch turtlebot3_gazebo turtlebot3_stage_{number_of_stage}.launch
```
To run the DRL code:
```
roslaunch project ddpg_stage_{number_of_stage}.launch
```

Credits: This is based on rcampbell95's branch
