# yolov8_ros2

## Required libraries
### Python3
```shell
pip install open3d
pip install ultralytics
```

```shell
mkdir -p ~/ros2_ws/src && cd ~/ros2_ws/src
git clone https://github.com/andreasHovaldt/yolov8_ros2.git
cd ~/ros2_ws
rosdep install --from-paths src --ignore-src -r -y
colcon build --symlink-install
source ~/ros2_ws/install/setup.bash
```

## Run code
```shell
ros2 launch yolov8_ros2 camera_yolo.launch.py
```
This launches the camera node, and the yolov8 node. 
The image prediction results of the yolov8 segmentation are published to the topic: ```/yolo/prediction/image```.
These results are also published in a json formatted string to the topic: ```/yolo/prediction/item_dict```.


