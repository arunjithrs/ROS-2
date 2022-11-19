# ROS2

### Install ros2 
https://docs.ros.org/en/humble/Installation/Ubuntu-Install-Debians.html

### Environment Setup
```
cd /opt/ros/humble
source setup.bash
```
```
cd
gedit ~/.bashrc
```
add his line at the end of the file
```
source /opt/ros/humble/setup.bash
```


### Launch a ROS2 program
```
# running the publisher
ros2 run demo_nodes_cpp talker

# running the subscriber
ros2 run demo_nodes_cpp listener
```

### Install Colcon
```
sudo apt install python3-colcon-common-extension
```


colcon setup
```
cd /usr/share/colcon_argcomplete/hook
gedit ~/.bashrc
```
add source at the end of the file
```
source /usr/share/colcon_argcomplete/hook/colcon-argcomplete.bash
```

### crate ROS2 workspace
```
mkdir ros2_ws
cd ros2_ws
mkdir src
colcon build
```
```
cd install/
source local_setup.bash
```

source it after source.bash and before colcon
```
gedit .bashrc
source ~/ros2_ws/install/setup.bash
```


### Create a python package
```
cd ros2_ws/src/
ros2 pkg create my_py_pkg --build-type ament_python --dependencies rclpy
```

build colcon
```
cd ros2_ws/
colcon build
```

for resolving humble package error
```
pip3 list
sudo apt install python3-pip
pip3 list | grep setuptools # current version 59.6.0
pip3 install setuptools==58.2.0
pip3 list | grep setuptools # not its 58.2.0

# build the colcon again
colcon build
```

continuing with build
``` 
colcon build ---packages-select my_py_pkg
```

### Create a C++ package
```
cd ros2_ws/src/
ros2 pkg create my_cpp_pkg --build-type ament_cmake --dependencies rclcpp
ls
```

# build the colcon again
```
cd ros2_ws/src/

colcon build
# or
colcon build ---packages-select my_cpp_pkg
```

