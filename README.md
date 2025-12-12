# Documentation

- [Documentation for the door parts](door_parts.md)
- [Requirements specification](requirements.md)
- [Manual for the Kinova Gen3 robot arm](manuals/EN-UG-014-Gen3-Ultra-lightweight-user-guide-r10.0.pdf)
- [Manual for the Robotiq 2F-85 gripper](manuals/2F-85_2F-140_Instruction_Manual_PDF_20181130.pdf)
- [Manual for the Robotiq FT 300-S force torque sensor](manuals/FT300-S_Sensor_Manual_general_PDF_20210831.pdf)

## Robot Setup

See the [eddie-ros repository](https://github.com/Robots4Sustainability/eddie-ros) for documentation on how to set up the robot and ROS2 workspace.

### Zenoh Config

When using Zenoh to run the perception nodes on the lab workstation, set the endpoint on your machine to the workstation IP address:

```bash
export ZENOH_CONFIG_OVERRIDE='connect/endpoints=["tcp/192.168.1.11:7447"]'
```

Start Zenoh on your machine afterwards:

```bash
ros2 run rmw_zenoh_cpp rmw_zenohd
```

## Links

- [Project Kanban](https://github.com/orgs/Robots4Sustainability/projects/1)
- Find API documentation for the Kinova arm in [this repo](https://github.com/Kinovarobotics/Kinova-kortex2_Gen3_G3L)
- [Schedule appointment to use robot](https://nc.uni-bremen.de/index.php/apps/calendar/appointment/qF4zidrge9nt)
- [Proposal document](https://typst.app/project/wYIco69fCEmJgELcsgiucs)
- [Robotiq support page](https://robotiq.com/support) for more documentation and software downloads
