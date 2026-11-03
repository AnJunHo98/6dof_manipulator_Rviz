# 6dof_manipulator_Rviz

ROS 1 URDF description of a 6-DOF arm (box geometry) with a launch file for viewing it in RViz.

## Overview

This repository contains one ROS 1 (catkin) package, `six_dof_arm_description`, that describes a six-joint robot arm (robot name `six_dof_arm`) in URDF. The links are modeled with simple box shapes, and six revolute joints (`joint1`–`joint6`) sit on a fixed base link. The launch file publishes the model so it can be posed with sliders and viewed in RViz.

## Repository layout

- `six_dof_arm_description/` – the catkin package
  - `urdf/six_dof_arm.urdf` – robot model (links, joints, joint limits)
  - `urdf/six_dof_arm.gv`, `urdf/six_dof_arm.pdf` – link/joint tree of the URDF as a Graphviz graph and its PDF rendering
  - `launch/six_dof_arm.launch` – loads the URDF as `robot_description` and starts `joint_state_publisher_gui` and `robot_state_publisher`
  - `package.xml`, `CMakeLists.txt` – package manifest and build rules

## Requirements

ROS 1 with catkin, `urdf`, `robot_state_publisher` and `joint_state_publisher_gui`.

## Usage

From a catkin workspace with the package under `src/`:

```bash
catkin_make
source devel/setup.bash
roslaunch six_dof_arm_description six_dof_arm.launch
```

The launch file does not start RViz. Open RViz separately, set the fixed frame to `base` and add a RobotModel display, then move the joints with the `joint_state_publisher_gui` sliders.

## Status

2022 project (single commit, September 2022), kept as a record and no longer maintained.

## License

No license file is included.
