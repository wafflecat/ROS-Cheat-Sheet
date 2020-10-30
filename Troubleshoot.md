# Common Errors and Fixes in ROS
A repository containing instructions for navigating the quirks of ROS.

## .bashrc Only Sourcing Last Workspace in .bashrc
https://www.theconstructsim.com/overlaying-ros-workspaces/

Sanity check with,
```bash
echo $ROS_PACKAGE_PATH
```
The fix is to just delete the build and devel folder of a workspace and rebuild,
```bash
cd ~/my_workspace
rm -rf build devel
catkin_make
source devel/setup.bash
```


