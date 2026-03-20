# visensor_MAML

A ROS package that subscribes to raw image data from a visual-inertial (VI) sensor and processes the frames using OpenCV. The package is intended for use with a Model-Agnostic Meta-Learning (MAML) pipeline.

## Prerequisites

- [ROS](http://wiki.ros.org/ROS/Installation) (tested with a standard desktop installation)
- [catkin](http://wiki.ros.org/catkin) and [catkin_simple](https://github.com/catkin/catkin_simple)
- Python 2 or 3
- OpenCV (`cv2`)
- `cv_bridge` (included in `ros-<distro>-cv-bridge`)
- `sensor_msgs` and `std_msgs` (included in a standard ROS installation)

## Installation

1. Clone this repository into your catkin workspace `src` directory:

   ```bash
   cd ~/catkin_ws/src
   git clone https://github.com/daiyk/visensor_MAML.git
   ```

2. Build the workspace:

   ```bash
   cd ~/catkin_ws
   catkin_make
   ```

3. Source the workspace:

   ```bash
   source ~/catkin_ws/devel/setup.bash
   ```

## Usage

Start the image listener node:

```bash
rosrun vimaml visensor_image.py
```

The node subscribes to the `/cam0/image_raw` topic. It converts incoming `sensor_msgs/Image` messages to OpenCV format and displays each frame in a window. Only frames larger than 60 × 60 pixels are processed.

## Package Structure

```
visensor_MAML/
├── CMakeLists.txt        # CMake build configuration
├── package.xml           # ROS package metadata
├── setup.py              # Python package setup for catkin
└── scripts/
    └── visensor_image.py # ROS image listener node
```

## License

See [package.xml](package.xml) for license information.
