Yd-LidarX2
This repository contains the ROS 2 workspace for the YDLidar X2, based on the original ydlidar_ros2_driver repository.
Forked repository: Ashutoshss/Yd-LidarX2, with modifications for the X2 model.

Setup Instructions
1. Create a ROS 2 Workspace
bash
Copy code
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
4. Set Up the YDLidar SDK
You will need the official YDLidar SDK.

Install CMake and Required Packages
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
cd YDLidar-SDK
mkdir ./build/
cd build
cmake ..
make
sudo make install
Install Python Package
bash
Copy code
cd ~/YDLidar-SDK
pip install .
Grant USB Permissions
bash
Copy code
sudo chmod 777 /dev/ttyUSB0
Run the Test Program
bash
Copy code
cd ~/YDLidar-SDK/build
./tri_test
5. Rebuild the ROS 2 Workspace
bash
Copy code
cd ~/ros2_ws
colcon build --symlink-install
6. Source the Environment
bash
Copy code
source ~/.bashrc
7. Launch the Driver
bash
Copy code
ros2 launch ydlidar_ros2_driver ydlidar_launch_view.py
Notes
Ensure that the baud rate and model-specific settings are correctly configured in the launch file or parameters.
For troubleshooting, refer to the YDLidar documentation.
