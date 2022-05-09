# openpose_ros

Example ROS catkin package that utilizes the OpenPose library from https://github.com/CMU-Perceptual-Computing-Lab/openpose.

## System
Tested on:
* Ubuntu 20.04
* ROS Noetic

## Installation Steps

1. Clone OpenPose somewhere not in your catkin_workspace.
   ```bash
   git clone https://github.com/CMU-Perceptual-Computing-Lab/openpose.git
   ```
2. IMPORTANT: I do not update this repository very frequently and the maintainers of OpenPose tend to change their API frequently, so I can only guarantee that it will work with certain versions of OpenPose. Currently I have updated this ros wrapper to work with commit b1cb2b6. You can use get that version by running the following commands:
   ```bash
   cd openpose
   git checkout b1cb2b6
   ```
3. Install openpose using instructions from here: https://github.com/CMU-Perceptual-Computing-Lab/openpose/blob/b1cb2b69cf8c4c288921e48c37f339a64db26f58/doc/installation/0_index.md. Make sure to run `sudo make install` in the build folder at the end.
4. Clone this repository into your catkin_workspace/src directory.
   ```bash
   git clone https://github.com/GJXS1980/openpose_ros.git
   cd openpose_ros/openpose_ros
   wget https://github.com/GJXS1980/openpose_ros/releases/download/v0.1/models.zip
   unzip models.zip

   ```
5. Modify the model_folder line in openpose_ros/src/openpose_flags.cpp to where openpose is installed (line 18).
   ```bash
   DEFINE_string(model_folder,             "/path/to/openpose/models/",      "Folder path (absolute or relative) where the models (pose, face, ...) are located.");
   ```
6. Modify the libs in openpose_ros/libs/

## Running
```bash
source catkin_workspace/devel/setup.bash
roslaunch openpose_ros openpose_ros.launch
```
