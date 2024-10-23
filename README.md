## Project Overview

This project simulates a mobile robot in CoppeliaSim using MATLAB to create a 2D occupancy grid map of a small rectangular environment. The robot is tested in two scenarios: manual teleoperation and autonomous wandering. The primary objectives are to maximize environment coverage and minimize mapping time. A comparative analysis is conducted between the efficiency of teleoperated mapping and autonomous mapping to highlight the trade-offs between human-controlled exploration and autonomous methods.

## Table of Contents
1. [Figures](#figures)
2. [Abbreviations](#abbreviations)
3. [System Requirements](#system-requirements)
4. [Project Setup](#project-setup)
5. [Key Technologies](#key-technologies)
6. [Mapping and Navigation](#mapping-and-navigation)
7. [Experiments](#experiments)
8. [Performance Analysis](#performance-analysis)
9. [Conclusion](#conclusion)
10. [Further Improvements](#further-improvements)

## Abbreviations
- **SLAM**: Simultaneous Localization and Mapping
- **LiDAR**: Light Detection and Ranging
- **A***: A-star (Pathfinding Algorithm)
- **MATLAB**: Matrix Laboratory programming language
- **URG**: Ultra-Range Finder (specific to Hokuyo sensors)
- **2D**: Two-Dimensional

## System Requirements
- **MATLAB** (with Robotics System Toolbox)
- **CoppeliaSim** (Robot Simulation Software)
- **LiDAR Sensor**: Hokuyo URG 04LX UG01 (used in simulation)
- **Pioneer 3-DX Mobile Robot** (virtual model in simulation)

## Project Setup
1. **Install MATLAB** and ensure you have the necessary toolboxes (Robotics System Toolbox).
2. **Install CoppeliaSim** to simulate the environment and robot interaction.
3. **Import Pioneer 3-DX Model** and **configure sensors** (LiDAR for environmental data capture).
4. **Install required libraries** in MATLAB to process sensor data and generate occupancy grids.

## Key Technologies
1. **SLAM**: Enables the robot to build a map while simultaneously tracking its location.
2. **A***: Pathfinding algorithm used for shortest path navigation in the environment.
3. **Pure Pursuit Algorithm**: Guides the robot to follow the planned path smoothly.

## Mapping and Navigation
- **Occupancy Mapping**: The environment is divided into grid cells, each categorized as free, occupied, or unknown. The robot uses LiDAR data to update this map as it explores the space.
- **Pathing**: The A* algorithm is used to calculate the most efficient route through free space, and the Pure Pursuit algorithm helps follow this route dynamically.

## Experiments

### 1. Teleoperation Mapping
- The robot is manually controlled by a human operator.
- **Results**: The manual mode exploration took 165 seconds to cover 98% of the area. The operator’s prior knowledge of the environment led to optimized movements.

### 2. Autonomous Mapping (Wandering Behavior)
- The robot explores the environment autonomously using real-time data without human intervention.
- **Results**: The autonomous mode exploration took 130 seconds to cover 98% of the area, showing a 24% improvement over the manual approach.

## Performance Analysis
- **Exploration Time**: Autonomous mapping was faster by 35 seconds compared to manual control.
- **Path Efficiency**: Human-controlled mapping was biased by prior knowledge, while autonomous mapping provided unbiased exploration based solely on sensor data.

## Conclusion
The project demonstrated the use of a mobile robot to autonomously map a 2D grid using SLAM in MATLAB, comparing teleoperation and autonomous wandering. While manual teleoperation can be faster due to human bias, autonomous mapping proved more scalable and unbiased, making it a better option for real-world applications like industrial inspections.

## Further Improvements
Several improvements are suggested:
1. **Blind Teleoperation Test**: To mitigate operator bias, blind testing would better simulate real-world conditions.
2. **Advanced Navigation Algorithms**: Implementing dynamic SLAM and sensor fusion could improve mapping accuracy and speed.
3. **Pose Estimation Enhancements**: Use advanced filters like the Extended Kalman Filter (EKF) to improve localization in dynamic environments.
4. **Testing in Complex Environments**: Introducing moving obstacles or varied terrain could further challenge and improve the robustness of the algorithms.



