Teleoperation Control of ROS-based Industrial Robot using EMG signals.

This System uses ROS in Ubuntu environments using PC. Robot Arm with 6 degree of freedom is controlled remotely using the EMG sensor. 
Robot arms and PC are wired together, and the electrostatic sensors are wirelessly connected to PC using Bluetooth adapters. 
Using ROS-communication, data about arm movements recognized by the EMG sensor is sent to the robot arm.

The robot arm moves in the same direction as the human movement, 
and the gripper moved on the robot arm is operated by a human hand gesture.


**Development Environment and Equipment**


Robot arm : UR3 (Universal Robots)

Gripper : 2F - 140 Gripper (Robotiq)

OS : Linux Ubuntu 16.04 (VirtualBox)

ROS : ROS Kinetic Kame

Sensor : Myo armband (Thalmic Labs)




**Working System**(in Ubuntu)


$ roscore

$ roslaunch ur_modern_driver ur3_bringup.launch robot_ip:= (input_your_ip)

$ rosrun ur_modern_driver myo-rawNode.py

$ rosrun robotiq_2f_gripper_control Robotiq2FGripperRtuNode.py /dev/ttyUSB0

$ rosrun robotiq_2f_gripper_control Robotiq2FGripperStatusListener.py

$ rosrun robotiq_2f_gripper_control Robotiq2FGripperSimpleController.py

$ rosrun ur_modern_driver RemoteUR3.py
