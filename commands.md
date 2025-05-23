This file contains useful commands and links.

## Commands

### robot-setup

create workspace
```
mkdir -p ~/r4s/src
cd ~/r4s
```

place the two files inside `~/r4s`
(the files can be found on discord on the "robot-setup" channel,
- colcon.meta
- r4s.repos
)

note: make sure you use the updated version of r4s.repos

then clone the repos
```
cd ~/r4s
vcs import src < r4s.repos
```

dependent libraries:
```
sudo apt install gstreamer1.0-tools gstreamer1.0-libav libgstreamer1.0-dev libgstreamer-plugins-base1.0-dev libgstreamer-plugins-good1.0-dev gstreamer1.0-plugins-good gstreamer1.0-plugins-base
```

run this in ~/r4s to install ros dependencies
```
rosdep install --from-paths . --ignore-src -r -y
```

clone the SOEM repo to your `~/`
```
cd ~/

git clone https://github.com/OpenEtherCATsociety/SOEM.git

cd SOEM

mkdir build && cd build

cmake -DBUILD_SHARED_LIBS=On -DCMAKE_INSTALL_PREFIX=/usr/local/ ..

sudo make install
```

```
sudo apt-get install python3-rosdep
```

```
cbp robif2b --cmake-args \
    -DENABLE_ETHERCAT=ON \
    -DENABLE_KELO=ON \
    -DENABLE_KORTEX=ON \
    -DCMAKE_BUILD_TYPE=Debug \
    -DENABLE_KORTEX_API_AUTO_DOWNLOAD=ON
```

In order to run:
`
ros2 run eddie-ros eddie_ros_interface --ros-args -p ethernet_if:=
`


## Links

use the `dev` branch of `robif2b` for gripper control: 
https://github.com/secorolab/robif2b/tree/dev

you will find API documentation in this repo:
https://github.com/Kinovarobotics/Kinova-kortex2_Gen3_G3L

schedule appointment to use robot:
https://nc.uni-bremen.de/index.php/apps/calendar/appointment/qF4zidrge9nt

Requirements document:
https://typst.app/project/w4eGOkZZURnUWsefWEqQz7

Proposal document (first draft):
https://typst.app/project/wYIco69fCEmJgELcsgiucs
