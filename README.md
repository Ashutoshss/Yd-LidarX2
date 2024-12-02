# YD-Lidar X2 ROS 2 Workspace

This repository contains a ROS 2 workspace for the **YDLidar X2**, based on the original `ydlidar_ros2_driver` repository. The workspace is modified to support the X2 model.

---

## Features
- ROS 2 support for YDLidar X2
- Based on the official `ydlidar_ros2_driver`
- Integrates the YDLidar SDK for optimal performance

---

## Setup Instructions

### 1. Create a ROS 2 Workspace
```bash
mkdir -p ~/ros2_ws/src
cd ~/ros2_ws
2. Clone the Repository
bash
Copy code
cd ~/ros2_ws/src
git clone https://github.com/Ashutoshss/Yd-LidarX2.git
3. Build the Workspace
bash
Copy code
cd ~/ros2_ws
colcon build --symlink-install
Setting Up the YDLidar SDK
Install Required Packages
bash
Copy code
sudo apt install cmake pkg-config
sudo apt-get install swig
sudo apt-get install python3-pip
Clone and Build the YDLidar SDK
bash
Copy code
mkdir -p ~/YDLidar-SDK
cd ~/YDLidar-SDK
git clone https://github.com/YDLIDAR/YDLidar-SDK.git
mkdir ./build/
cd build
cmake ..
make
sudo make install
Install the Python Package
bash
Copy code
cd ~/YDLidar-SDK
pip install .
Grant USB Permissions
bash
Copy code
sudo chmod 777 /dev/ttyUSB0
Test the YDLidar SDK
bash
Copy code
cd ~/YDLidar-SDK/build
./tri_test
Finalizing the ROS 2 Workspace
4. Rebuild the ROS 2 Workspace
bash
Copy code
cd ~/ros2_ws
colcon build --symlink-install
5. Source the Environment
bash
Copy code
source ~/.bashrc
Running the Driver
Launch the Driver
bash
Copy code
ros2 launch ydlidar_ros2_driver ydlidar_launch_view.py
Notes
Baud Rate: Ensure the correct baud rate is configured for the YDLidar X2. By default, it is set to 115200.
Model-Specific Settings: Adjust parameters in the launch file or parameter configuration files as needed.
Troubleshooting: Refer to the YDLidar Documentation for detailed information on common issues.
