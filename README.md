# Teleop_Robot
Install ROS Noetic in ubantu or linux OS by following the following tutorial
http://wiki.ros.org/noetic/Installation/Ubuntu

Download this folder and run the following commands

Catkin_make


source devel/setup.bash


roslaunch teleop_description gazebo.launch


roslaunch teleop_description display.launch


actor plugin with cmd_vel topic
	<actor name="actor">
	  <pose>-7.5 5 1.01 0 0 0</pose>
	  <skin>
	    <filename>walk.dae</filename>
	  </skin>
	  <animation name="walking">
	    <filename>walk.dae</filename>
	    <interpolate_x>true</interpolate_x>
	  </animation>
	  <collision name="collision">
	    <geometry>
	      <cylinder>
		<radius>0.12</radius>
		<length>0.9</length>
	      </cylinder>
	    </geometry>
	  </collision>
	  <visual name="visual">
	    <geometry>
	      <cylinder>
		<radius>0.12</radius>
		<length>0.9</length>
	      </cylinder>
	    </geometry>
	  </visual>
	      <plugin name="actor_plugin" filename="libgazebo_ros_actor_command.so">
        <!-- <follow_mode>path</follow_mode> -->
        <follow_mode>velocity</follow_mode>
        <vel_topic>/cmd_velp</vel_topic>
        <path_topic>/cmd_path</path_topic>
        <animation_factor>4.0</animation_factor>
        <linear_tolerance>0.1</linear_tolerance>
        <linear_velocity>1</linear_velocity>
        <angular_tolerance>0.0872</angular_tolerance>
        <angular_velocity>2.5</angular_velocity>
        <default_rotation>1.57</default_rotation>
      </plugin>  
	  
	</actor>
