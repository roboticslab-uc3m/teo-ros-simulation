# teo_control

This package contains the configuration of all the different controllers used during the simulation, and the launch files for it's initialization. It uses ros_control with this porpouse. 

## How it works

The general scheme of this package can be seen in the following figure.


![alt tag](http://i.imgur.com/9gqOS70.jpg?1)

- **teo_controllers.launch:** This launch is in charge to init the controller_spawner which is part of the ros_control architecture, and it's goal it is to spawn all the different controllers in the simulation with the corresponding configuration specified in the teo_controllers.yaml file.

- **robot_state_publisher:** This node is in charge to publish the tf of the robot. Take a look to <http://wiki.ros.org/robot_state_publisher> for more info.
