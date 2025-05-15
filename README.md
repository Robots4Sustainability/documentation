# Documentation

- [Documentation for the door parts](door_parts.md)

## Robot Setup

### Requirements

- Ubuntu 24.04
- ROS 2 Jazzy: Follow the instructions in the [ROS 2 installation guide](https://docs.ros.org/en/jazzy/Installation/Ubuntu-Install-Debs.html)
- SSH keys set up for your GitHub account: Follow the instructions in the [GitHub SSH key guide](https://docs.github.com/en/authentication/connecting-to-github-with-ssh/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent) to generate a new SSH key and add it to your account.

`rosdep` for installing dependencies. Install it with:

```bash
sudo apt install python3-rosdep
```

`rosdep` needs to be initialized and updated to use:

```bash
sudo rosdep init
rosdep update
```

### Setup steps for ROS

Install the following dependencies:

```bash
sudo apt install gstreamer1.0-tools gstreamer1.0-libav libgstreamer1.0-dev libgstreamer-plugins-base1.0-dev libgstreamer-plugins-good1.0-dev gstreamer1.0-plugins-good gstreamer1.0-plugins-base
```

1. Create a ROS workspace directory and navigate to it:

```bash
mkdir -p ~/r4s/src
cd ~/r4s
```

2. Copy `r4s.repos` to the `r4s` directory and clone the required repositories:

```bash
vcs import src < r4s.repos
```

3. Install the dependencies using `rosdep`:

```bash
rosdep install --from-paths src --ignore-src -y -r
```

4. Copy `colcon.meta` to the `r4s` directory and build the workspace with `colcon`:

```bash
colcon build
```

You can now source the workspace:

```bash
source install/setup.bash
```

### Setup steps for SOEM

To communicate with the robot base using EtherCAT, you need to install the SOEM library.

1. Clone the SOEM repository into your home directory and navigate to it:

```bash
cd ~/
git clone https://github.com/OpenEtherCATsociety/SOEM.git
cd SOEM
```

2. Create a build directory and navigate to it:

```bash
mkdir build
cd build
```

3. Build the SOEM library with CMake and install it:

```bash
cmake -DBUILD_SHARED_LIBS=On -DCMAKE_INSTALL_PREFIX=/usr/local/ ..
sudo make install
```
