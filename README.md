# EGH400-2-Rev-Aero-Simulator (Thesis)

### Installation and Initial Setups
This document will step through the process of installing ROS, Gazebo and Ardupilot. 
The following set of instructions also provides sample code that can be executed to see if the installation process was successful. 

#### Note: All links provided alone are from a channel called "Intelligent Quads". No material except for any files edited (will be listed below) is not my work and all credit goes to Intelligent Quads. There are other sets of Youtube videos by the same channel if you have an older version of Linux, this set of instructions is only suitable for Ubuntu 20.04.3.

It is reccomended to follow the youtube video (link below) as it provides visuals on what the installation should look like.                       
https://www.youtube.com/watch?v=1FpJvUVPxL0&ab_channel=IntelligentQuads

The Youtube video runs through the following set of tutorials (in order).                                                                                              
https://github.com/Intelligent-Quads/iq_tutorials/blob/master/docs/Installing_Ardupilot_20_04.md

https://github.com/Intelligent-Quads/iq_tutorials/blob/master/docs/installing_gazebo_arduplugin.md

https://github.com/Intelligent-Quads/iq_tutorials/blob/master/docs/installing_ros_20_04.md

### Edited Files
This section will outline the files edited so far. These files are subject to change as the project progresses. The following files have been changes to fit the 20 UAV criteria. Intelligent Quads provides more information in their videos to why these files need to be edited and how the simulator works generally. It is reccomended to watch their videos before experimenting as it provides a lot of background information. Download the files in this repository and place them in the locations listed. 

default_params(Whole folder) -> `.../ardupilot/Tools/autotest`

vehicleinfo.py -> `.../ardupilot/Tools/autotest/pysim` 

multi_apm.launch -> `.../catkin_ws/src/iq_sim/launch`

multi_drone.world -> `.../catkin_ws/src/iq_sim/worlds`

drone1-20 (all folders) -> `.../catkin_ws/src/iq_sim/models`

multi_square.launch -> `.../catkin_ws/src/iq_gnc/launch`

square.cpp -> `.../catkin_ws/src/iq_gnc/src`

multi_sitl.sh -> `/home (You can run this anywhere as long as you convert it into an executable)`

### Running the Simulation
Run Gazebo
```
roslaunch iq_sim multi_drone.launch
```
Run Ardupilot Instances
```
./multi_sitl.sh
```
Run MAVROS Instances
```
roslaunch iq_sim multi_apm.launch
```
Run Guidance Program (Wait for all UAVs to connect to GPS before executing this line)
```
roslaunch iq_gnc multi_square.launch
```
