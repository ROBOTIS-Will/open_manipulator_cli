# open_manipulator_cli
OpenManipulator-X Command Line Interface.  
This package requires ROBOTIS [open_manipulator_msgs package](https://github.com/ROBOTIS-GIT/open_manipulator_msgs).


# Setup

```bash
$ cd ~/catkin_ws/src
$ git clone https://github.com/ROBOTIS-Will/open_manipulator_cli.git
$ cd ~/catkin_ws && catkin_make
```

# Usage
## Joint Space control
Enter each joint angle in `radian` and time in `second`.  
**rosrun open_manipulator_cli moveJointSpace.py [joint1] [joint2] [joint3] [joint4] [time]**
- Go to Home Pose for 3 seconds
  ```bash
  $ rosrun open_manipulator_cli moveJointSpace.py 0.0 -1.05 0.35 0.7 3.0
  ```

## Task Space control
Enter the coordinate of the endeffector in `meter` and time in `second`.  
**rosrun open_manipulator_cli moveTaskSpace.py [x] [y] [z] [time]**
- Go to Init Pose for 3 seconds
  ```bash
  $ rosrun open_manipulator_cli moveTaskSpace.py 0.286 0.0 0.204 3.0
  ```
  
## Gripper Control
Enter the gripper opening value in `meter` and time in `second`.  
Gripper Position Range : -0.01 ~ 0.01  
**rosrun open_manipulator_cli moveGripper.py [gripper_position] [time]**
- Open the gripper to max width
  ```bash
  $ rosrun open_manipulator_cli moveGripper.py 0.01 1.0
  ```
  
## Torquen Enable / Disable
Turn on or off the torque of DYNAMIXEL.  
**rosrun open_manipulator_cli setDynamixelTorque.py [on|off]**
- Turn on DYNAMIXEL Torque
  ```bash
  $ rosrun open_manipulator_cli setDynamixelTorque.py on
  ```

## Read Manipulator Moving Status
Read whether the OpenManipulator is in motion or not (except the gripper).
```bash
$ rosrun open_manipulator_cli readMovingStat.py
```
