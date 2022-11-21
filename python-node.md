### Create node in python
```
cd my_py_pkg
mkdir my_py_pkg
touch my_first_node.py
```

my_first_node.py
```
#!/usr/bin/env python3
import rclpy
from rclpy.node import Node


def main(args=None):
    rclpy.init(args=args)
    node = Node("py_test")
    node.get_logger().info("Hello ros2")
    rclpy.spin(node)
    rclpy.shutdown()


if __name__ =='__main__':
    main()
```
make the file executable
```
sudo chmod +x my_first_node.py
```
run the code in pytho
```
. my_first_node.py
```

Install the code with python

inside ``consols script :[]`` in setup.py add the following code inside array
```
my_node = my_py_pkg.my_first_node:main
```
go to workspace
``` 
cd ros2_ws
```
build colcon
```
colcon build --packages-select my_py_pkg

#sourcing again (not needed all the time)
source ~/.barshrc
```

now it will be available to run the script with ros2 run command
```
ros2 run my_py_pkg py_node
```

as per the ``setup.cfg`` package is availbale under ``~/ros2_ws/install/my_py_pkg/lib/my_py_pkg/`` directory



