cmake_minimum_required(VERSION 2.8.3)

project(urdfgenesyssw)

find_package(catkin REQUIRED
  gazebo_ros
  gazebo_ros_control
  joint_state_publisher
  robot_state_publisher
  roscpp
  rospy
  rviz
  sensor_msgs
  std_msgs
  tf
  xacro
  urdf
  controller_manager
)

catkin_package()

find_package(roslaunch)

foreach(dir config launch meshes urdf)
	install(DIRECTORY ${dir}/
		DESTINATION ${CATKIN_PACKAGE_SHARE_DESTINATION}/${dir})
endforeach(dir)
