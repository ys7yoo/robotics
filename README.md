## Installing ROS on Raspberry Pi

* Follow instructions [here](http://wiki.ros.org/melodic/Installation/Ubuntu)
```
sudo sh -c 'echo "deb http://packages.ros.org/ros/ubuntu $(lsb_release -sc) main" > /etc/apt/sources.list.d/ros-latest.list'

curl -sSL 'http://keyserver.ubuntu.com/pks/lookup?op=get&search=0xC1CF6E31E6BADE8868B172B4F42ED6FBAB17C654' | sudo apt-key add -
```

* [Build from sorce](http://wiki.ros.org/melodic/Installation/Source) for Raspberry Pi

```
sudo apt-get install python-rosdep python-rosinstall-generator python-wstool python-rosinstall build-essential

sudo rosdep init
rosdep update

mkdir ~/ros_catkin_ws
cd ~/ros_catkin_ws
```

```
rosinstall_generator desktop --rosdistro melodic --deps --tar > melodic-desktop.rosinstall
wstool init -j8 src melodic-desktop.rosinstall
```

```
./src/catkin/bin/catkin_make_isolated --install -DCMAKE_BUILD_TYPE=Release
```
