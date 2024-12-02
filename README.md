# Yd-LidarX2
This repo contains ROS2 Workspace of Ydlidar-X2 
original repo ``` https://github.com/YDLIDAR/ydlidar_ros2_driver.git```
fork reop ``` https://github.com/Ashutoshss/Yd-LidarX2.git ```
with some change to the repo for my X2

make a workspace ```mkdir -p ~/ros2_ws/src```
build it ```colcon build --symlink-install```
clone the repo ``` git clone https://github.com/Ashutoshss/Yd-LidarX2.git ```

we also need to setup the ydlidar_sdk
from official https://github.com/YDLIDAR/YDLidar-SDK.git

additionally
Install CMake
sudo apt install cmake pkg-config

Install Extra
sudo apt-get install swig
sudo apt-get install python3-pip

mkdir -p ~/YDLidar-SDK
git colne https://github.com/YDLIDAR/YDLidar-SDK.git
cd YDLidar-SDK
mkdir ./build/
cd YDLidar-SDK/build
cmake ..
make
sudo make install
cd YDLidar-SDK
pip install .
cd
sudo chmod 777 /dev/ttyUSB0
cd ~/YDLidar-SDK/build
./tri_test

build it again```colcon build --symlink-install```
source ~/.bashrc
