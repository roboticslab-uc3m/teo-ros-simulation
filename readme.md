# teo-ros-simulation
This repository provides the needed files to run a simulation of the UC3M humanoid robot TEO in ros.

## Installation steps

This package is devoloped for the ROS INDIGO version, any different ROS version may not be supported. For the correct setup of the packages follow the next steps.

1. **Clone** this repository in a catkin_workspace. See this totorial <http://wiki.ros.org/catkin/Tutorials/create_a_workspace> to create a catkin_workspace in ROS.
2. Use **rosdep** to install al the needed dependencies. For this you just can run the following command.

	```
		rosdep install teo_control
	```
3. **Compile** the project with the following commands

	```
		cd "your_catkin_ws_route"

		catkin_make	
	```

## Overall scheme
The general working scheme of this repository is represented in the following image.

![alt tag](http://i.imgur.com/IcHvehz.jpg?1)

- **teo.launch:** is in charge of the initialization and control of all the system.
 - **empty_world.launch:** is a third-party Gazebo launch which is in charge to init a gazebo empty world environment where later we will spawn our robot.
- **spawn_robot.launch:** this launch it's in charge to spawn the robot in the Gazebo environment, for that it uses the teo_humanoid.urdf.xacro file as the description of the robotic model.
- **teo_control.launch:** here all the simulated controllers needed for the simulation are initialized and configured.It uses ros_control with this porpouse. For a deeper understanding about how this is done take a look to the teo_control package documentation.

## teo_description

This package contains the meshes and urdf files for the UC3M humanoid robot TEO, needed for running a simulation in ROS.

## teo_gazebo

This ROS package contains all the needed launch files, for running a gazebo simulation of TEO. It also contains the definition of different world, to make possible to change the simulation environment to the user.

## teo_control

This package contains the configuration of all the different controllers used during the simulation, and the launch files for it's initialization. It uses ros_control with this porpouse. For a deeper understanding about how this is done take a look to the teo_control package documentation.

### Note
This package is based in the package presented in the following repository <https://github.com/roboticslab-uc3m/teo_robot>

