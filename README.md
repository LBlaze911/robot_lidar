# Robot Simulation and Obstacle Detection Project

Welcome to the repository for our final-year engineering project! This project involves the simulation of our robot using ROS, along with hardware integration featuring a LiDAR sensor and a front-facing camera for obstacle detection, powered by a Raspberry Pi.

---

## Features

### 1. **Robot Simulation**
- **Environment:** Simulated in Gazebo with realistic physics and dynamics.
- **Model:** A custom 4-wheeled robot designed for mobility and obstacle avoidance tasks.
- **ROS Integration:** Full compatibility with ROS for controlling robot movement and sensor data processing.

### 2. **Hardware Integration**
- **LiDAR Sensor:** Implemented for real-time environment mapping and obstacle detection.
- **Front-Facing Camera:** Configured to provide visual input for detecting obstacles using image processing techniques.
- **Raspberry Pi:** Used as the onboard computing unit to process sensor data and execute control algorithms.

### 3. **Obstacle Detection and Avoidance**
- Combines LiDAR and camera data for accurate detection and avoidance of obstacles.
- Efficient algorithms for real-time processing and decision-making.

---

## Technologies and Tools

- **Simulation:** ROS Humble, Gazebo 11
- **Programming Languages:** Python, C++
- **Hardware:**
  - Raspberry Pi 4
  - LiDAR Sensor (e.g., RPLIDAR A1)
  - USB or Pi Camera Module
- **Libraries and Frameworks:**
  - OpenCV for image processing
  - PCL (Point Cloud Library) for LiDAR data
  - ROS packages: `gmapping`, `move_base`, `rviz`

---

## Installation and Setup

### Prerequisites
1. Ubuntu 20.04
2. ROS Humble installed
3. Gazebo 11
4. Python 3.8 or higher

### Steps
1. Clone the repository:
   ```bash
   git clone https://github.com/LBlaze911/robot_lidar.git
   cd robot_lidar
   ```
2. Install dependencies:
   ```bash
   sudo apt-get update
   rosdep install --from-paths src --ignore-src -r -y
   ```
3. Build the workspace:
   ```bash
   catkin_make
   source devel/setup.bash
   ```
4. Launch the simulation:
   ```bash
   roslaunch robot_lidar simulation.launch
   ```

---

## Usage

### Simulation
- Launch the Gazebo environment:
  ```bash
  roslaunch robot_project gazebo.launch
  ```
- Control the robot using teleoperation or autonomous navigation.

### Hardware
- Connect the LiDAR sensor and camera to the Raspberry Pi.
- Run the onboard processing node:
  ```bash
  roslaunch robot_lidar hardware.launch
  ```
  
---

## Project Structure
```
robot_lidar/
├── src/
│   ├── robot_control/
│   ├── obstacle_detection/
│   ├── lidar_processing/
│   └── camera_processing/
├── launch/
│   ├── simulation.launch
│   ├── gazebo.launch
│   └── hardware.launch
└── urdf/
    └── robot_model.urdf
```

---

## Future Enhancements
- Implement SLAM for real-time mapping and navigation.
- Optimize obstacle detection using machine learning models.
- Add additional sensors (e.g., ultrasonic sensors) for improved robustness.

---

Thank you for visiting this repository and showing interest in my project!


# Lidar

sudo chmod 777 /dev/ttyUSB0

cd src/rplidar_ros
source scripts/create_udev_rules.sh

ros2 launch rplidar_ros view_rplidar_a1_launch.py