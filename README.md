# RoboND Go Chase It!

This repository uses Git submodules. To clone it, run

```bash
git clone --recursive git@github.com:sunsided/RoboND-GoChaseIt.git
```

Note that the submodules point to this very repo and live in the `my_robot` and `ball_chaser` branches. 

## Running the code

To run the world, run:

```bash
roslaunch my_robot world.launch
````

To run the ball chasing controller, tun:

```bash
roslaunch ball_chaser ball_chaser.launch
```

## Building with CLion IDE

**Note:** This does not _really_ work, as CLion will be unable to find generated headers. It's still a bit
          better than doing everything the hard way.

The full requirements for setting up CLion are given in the [sunsided/robond-ros-docker](https://github.com/sunsided/robond-ros-docker)
repository. In short, run SSHD in Docker, configure a Remote Host build to connect to it, then configure
the your build settings for ROS. For this repo and the included Dockerfile, this configuration will do:

**CMake options:**

```
-DCATKIN_DEVEL_PREFIX:PATH=/workspace/devel -DCMAKE_PREFIX_PATH=/workspace/devel;/opt/ros/kinetic;/opt/ros/kinetic/share
```

**Environment:**

```
ROS_ROOT=/opt/ros/kinetic/share/ros;ROS_PACKAGE_PATH=/workspace/src:/opt/ros/kinetic/share;ROS_MASTER_URI=http://localhost:11311;ROS_PYTHON_VERSION=2;ROS_VERSION=1;ROSLISP_PACKAGE_DIRECTORIES=/workspace/devel/share/common-lisp;ROS_DISTRO=kinetic;ROS_ETC_DIR=/opt/ros/kinetic/etc/ros;PYTHONPATH=/opt/ros/kinetic/lib/python2.7/dist-packages;PKG_CONFIG_PATH=/workspace/devel/lib/pkgconfig:/opt/ros/kinetic/lib/pkgconfig:/opt/ros/kinetic/lib/x86_64-linux-gnu/pkgconfig;LD_LIBRARY_PATH=/workspace/devel/lib:/opt/ros/kinetic/lib:/opt/ros/kinetic/lib/x86_64-linux-gnu:$LD_LIBRARY_PATH;PATH=/opt/ros/kinetic/bin:$PATH
```
