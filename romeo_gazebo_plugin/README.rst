romeo_gazebo_plugin
=================

Package developed against ROS Indigo and default gazebo (gazebo 2.2.3)

Dependencies
------------

The package requires romeo_description and romeo_control package

.. code-block:: bash

    sudo apt-get install ros-indigo-romeo-description
    sudo apt-get install ros-indigo-romeo-control

Other plugins to fetch and compile:

.. code-block:: bash
    
    git clone git@github.com:roboticsgroup/roboticsgroup_gazebo_plugins.git
    git clone git@github.com:pal-robotics/pal_msgs.git
    git clone git@github.com:pal-robotics/pal_gazebo_plugins.git
    catkin_make

Please also make sure that the package and all the dependencies are up to date

.. code-block:: bash
    
    sudo apt-get update


How to run it
-------------

.. code-block:: bash
    
    roslaunch romeo_gazebo_plugin romeo_gazebo_plugin_H37.launch


This will spawn gazebo with Romeo on a robocup field.
The ball has the same specs as the official RoboCup ball (size and mass).

The simulation will be in pause mode to allow initialization of all the controllers.
Wait until eveything is successfully loaded: 

.. code-block:: bash
    
    [INFO] [WallTime: 1413899465.061789] [0.000000] Controller Spawner: Loaded controllers: /romeo_dcm/Head_controller, /romeo_dcm/RightArm_controller, /romeo_dcm/LeftArm_controller, /romeo_dcm/LeftLeg_controller, /romeo_dcm/RightLeg_controller, /romeo_dcm/RightHand_controller, /romeo_dcm/LeftHand_controller, /romeo_dcm/joint_state_controller


Click the Play button.

Your Romeo should be standing in front of the ball at the center of the field.


Get sensor data from gazebo
---------------------------

All the sensors are simulated using plugins. These plugins are included in the robot description via romeoGazebo.xacro file. 
Each sensor publish data on rostopics. 

We can visualize topics using Ctrl+T or Window/Topic Visualization

.. image:: images/TopicVisu.png   
   :width: 100%

For example, visualizing Cameras and sonar

.. image:: images/GazeboCamSonar.png
   :width: 100%


We can also visualize these messages using Rviz plugins

.. image:: images/MoveitCamSonar.png
   :width: 100%


How to interact with simulated robot
------------------------------------

Using MoveIt!:

To control your simulated robot using MoveIt, run:

.. code-block:: bash

    roslaunch romeo_moveit_config moveit_planner.launch


Then you can control the robot with MoveIt!, check the tutorial quick tutorial here https://github.com/ros-aldebaran/romeo_moveit_config/blob/master/README.rst
