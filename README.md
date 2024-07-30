Intelligent robot programming using Robot Operating System (ROS), version: ROS 2 Humble

By: Dhruvsanjay Pathak ID: 19067960 and Manraj Singh Gill 
steps: 
1 open terminal
2 cd project_ws
3 colcon build --symlink-install 
4 source install/setup.bash 
5 ros2 launch trion_bot rsp.launch.py
6 open another terminal tab
7 rviv2 for simulation 
8 python3 -m serial.tools.miniterm /dev/ttyUSB0 57600
9 ros2 launch trion_bot launch_sim.launch.py
10 ros2 run teleop_twist_keyboard teleop_twist_keyboard 
11 ros2 run joint_state_publisher_gui joint_state_publisher_gui
12 ros2 run rqt_image_view rqt_image_view
13 ros2 run rplidar_ros rplidar_composition --ros-args -p serial_port:=/dev/ttyUSB0 -p serial_baudrate:=115200 -p frame_id:=laser_frame -p angle_compensate:=true -p scan_mode:=Standard
14 ros2 run teleop_twist_keyboard teleop_twist_keyboard --ros-args -r /cmd_vel:=/diff_cont/cmd_vel_unstamped 
15 ros2 run controller_manager spawner.py diff_cont
16 ros2 run controller_manager spawner.py joint_broad
All copyrights reserved to Trion Robotics. # robot_ws

Git update:
cd ~/robot_ws/src/trion_bot
git status
git add .
git commit -m "changes"
git push origin master
