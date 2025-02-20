# px4_keyboard_control
![GitHub last commit](https://img.shields.io/github/last-commit/aktamaa/px4_keyboard_control)

ROS2-based Keyboard Control Code to Control a PX4 Multicopter.

This code supports both **Position** and **Velocity** control for the **Offboard** mode in PX4. It has been tested in simulation and through field tests on a drone. It is working with MicroXRCE middleware.

## Installation
Before building this package, please install the [px4_msgs](https://github.com/PX4/px4_msgs) in advance.
```bash
mkdir -p ~/px4_control_ws/src
cd ~/px4_control_ws/src
git clone https://github.com/aktamaa/px4_keyboard_control.git
cd ..
colcon build --symlink-install
```

## Run The Nodes
In the first terminal, do:
```bash
ros2 run px4_keyboard_control px4_keyboard_handler
```

In the second terminal, do:
```bash
ros2 run px4_keyboard_control px4_offboard_control
```

## Command List
`t`: Arm the drone  
`y`: Disarm the drone  
`o`: Switch to Offboard mode  
`g`: Switch to Land mode  
`p`: Switch to Position Control mode  
`v`: Switch to Velocity Control mode  
`b`: Brake/Stop in Velocity Control mode (zeroing velocity)
`q`: Exit (stop the node)

### Movement Commands in Position Control Mode
In position control mode, each movement command moves the drone **1 meter** from its current position.

`w`: Move upward  
`s`: Move downward  
`a`: Rotate left (yaw left)  
`d`: Rotate right (yaw right)  
`i`: Move forward  
`k`: Move backward  
`j`: Move left (roll left)  
`l`: Move right (roll right)  

### Movement Commands in Velocity Control Mode
In velocity control mode, each movement command **increases the drone's velocity by 0.5** in the specified direction.

`w`: Increase upward velocity (ascend)  
`s`: Increase downward velocity (descend)  
`a`: Increase rotation velocity to the left (yaw left)  
`d`: Increase rotation velocity to the right (yaw right)  
`i`: Increase forward velocity  
`k`: Increase backward velocity  
`j`: Increase leftward velocity (roll left)  
`l`: Increase rightward velocity (roll right)  
