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
catkin init
catkin config --extend /opt/ros/indigo
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


### neo_triniry.rosinstall

All the packages for talking to the Trinity modules in the NEO.

### ltu_vicon.rosinstall

LTU's Vicon packages.

### kfly_telemetry.rosinstall

Coming soon!
