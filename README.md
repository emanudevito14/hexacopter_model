This repository is designed to be utilized together with [PX4-Autopilot](https://github.com/PX4/PX4-Autopilot),PlotJuggler,[px4_msg](https://github.com/PX4/px4_msgs/tree/main) and 
[QGroundControl](https://docs.qgroundcontrol.com/Stable_V5.0/en/qgc-user-guide/getting_started/download_and_install.html)

Clone this repository
```
git clone https://github.com/emanudevito14/hexacopter_model.git
 
```
Add hex_6 folder in PX4-Autopilot/Tools/simulation/gz/models

Replace the hexacopter_model's airframes folder with the folder of the same name located at this path PX4-Autopilot/ROMFS/px4fmu_common/init.d-posix/

Replace the hexacopter_model's uxrce_dds_client folder with the folder of the same name located at this path PX4-Autopilot/src/modules/

Clone px4_msg in ros2_ws/src
```
git clone https://github.com/PX4/px4_msgs.git
cd cd px4_msgs
git checkout release/1.16

```
Go in ros2_ws
```
colcon build --packages-select px4_msgs
source install/setup.bash
```
Go in PX4-Autopilot folder 
```
make px4_sitl gz_hex_6
```
Open the application QGroundControl click on takeoff and select flight position mode 

Open new terminal and run DDS_run.sh that you can find [here](https://github.com/RoboticsLab2025/aerial_robotics)
```
./DDS_run.sh

```
Opne new terminal in ros2_ws
```
source install/setup.bash
ros2 topic echo /fmu/out/actuator_output
```
Open new terminal in ros2_ws
```
ros2 run plotjuggler plotjuggler
```
In plotjuggler application following this [video](https://www.youtube.com/watch?v=6kRTiCn-lfw&t=20s)

