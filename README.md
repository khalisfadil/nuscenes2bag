# Autobin2bag
This repository is forked from *https://github.com/clynamen/nuscenes2bag*.
It is adjusted so that it can be use to convert files from Autobin dataset into a Rosbag

Its loads the json metadata and then sample files for each scene and converted into a respected ROS msg and written into a bag.

## Installation

**ROS-Noetic**

copy this repository into a folder *catkin_ws/src*. Resource your ROS-Noetic and build the node.
```
$ mkdir -p ~/catkin_ws/src
$ cd ~/catkin_ws/src
$ git clone https://github.com/khalisfadil/nuscenes2bag.git
$ cd ..
$ source /opt/ros/noetic/setup.bash
$ catkin_make
$ source devel/setup.bash
```

**Command-line arguments:**

`--dataroot`: The path to the directory that contains the 'maps', 'samples' and 'sweeps'.

`--version`: (optional) The sub-directory that contains the metadata .json files. Default = "v2.0"

**Dataroot**

The `--dataroot` supposely have this sub-folder inside:

1. __Sweeps__ - to put all your sweeps data

2. __Samples__ - to put all your samples data

3. __v2.0__ - include metadata which in json format

**Converting datasets:**

Convert a dataset with the metadata in a sub-directory called 'v2.0':
```
rosrun nuscenes2bag nuscenes2bag --dataroot /path/to/nuscenes_data_v2.0/ --version v2.0 --out nuscenes_bags/ --jobs 4
```
