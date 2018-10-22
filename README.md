# Collection of .rosinstall files

## Description

Using wstool to automatically clone all packages needed for some functionality.

## Extending this repository

1. Fork this repository
2. Add your .rosinstall files
3. Update the bottom of README.md with a description for each file
4. Create a pull request

## Using wstool

### First step

Create a catkin workspace where all the packages will be, together with the source folder.

Example:

```
mkdir -p ~/catkin_ws/src
cd ~/catkin_ws
catkin init
catkin config --extend /opt/ros/kinetic
```

Or one-liner:

```
cd ~/catkin_ws
catkin config --mkdirs --extend /opt/ros/kinetic --cmake-args -DCMAKE_EXPORT_COMPILE_COMMANDS=1 -DCMAKE_BUILD_TYPE=Release
```

### Populate src folder using wstool

Go to the catkin workspace:

`cd ~/catkin_ws`

Populate the src folder:

`wstool init src ROSINSTALL_FILE.rosinstall`

### Add more .rosinstall files

Merge the new install file with the existing src folder:

`wstool merge -t src NEXT_ROSINSTALL_FILE.rosinstall`

### Updating (pulling latest changes)

To update or pull the latest changes run:

`wstool update -t src`

### Finalizing

Now you can build the workspace as normally using `catkin build`.

---

## Available install files

### `msf.rosinstall`

Multi sensor fustion packages.


### `rosflight_comm.rosinstall`

All the packages for talking to the ROSFLIGHT system and converting messages to `mav_comm`.

### `px4_comm.rosinstall`

All the packages for talking to the PX4 and converting messages to `mav_comm`.

### `neo_trinity.rosinstall`

All the packages for talking to the Trinity modules in the NEO.

### `ltu_vicon.rosinstall`

LTU's Vicon packages.

### `sonar_array.rosinstall`

LTU's sonar array system for collision avoidance.

