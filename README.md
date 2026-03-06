<h1 align="center"> Eurobot 2026: Main Robot Simulation in Gazebo </h1>

This repository contains the complete simulation of my robotics team's main robot for the Eurobot 2026 competition. It focuses on high-fidelity physics and sensor integration to validate navigation algorithms before implementing them on the physical hardware. 

The simulation is developed using ROS 2 Humble and Gazebo, providing a robust digital twin for development.

## 🛠️ Key Features
### 1. Robot Modeling (URDF)
- `robot_description`: A complete and modular URDF (Unified Robot Description Format) representing the robot's physical dimensions, visual meshes, and collision boundaries.

- Frame Validation: Fully calibrated transform tree (TF) validated via RViz2 to ensure sensor mounting points and wheel centers are mathematically accurate.

### 2. Physics & Control
- `ros2_control` Integration: Implementation of a Mecanum Drive Controller. This allows for omnidirectional movement, simulating the complex kinematics of the robot's 4-wheel omnidirectional drive.

- Gazebo: A configured world with realistic friction coefficients and gravity to test motor torque and acceleration profiles.

### 3. Sensor Suite (Simulated)
To achieve autonomous navigation, the following sensors have been integrated and piped into ROS 2 topics:

- LiDAR: 360° laser scanner for obstacle detection and SLAM.

- IMU (Inertial Measurement Unit): Provides orientation and angular velocity data, essential for EKF (Extended Kalman Filter) fusion.

- Odometry: Real-time position tracking calculated from wheel encoders within the ros2_control loop.
