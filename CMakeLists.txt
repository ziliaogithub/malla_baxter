cmake_minimum_required(VERSION 2.8.3)
project(baxter_vicon_teleop)

find_package(catkin REQUIRED COMPONENTS
	geometry_msgs
	std_msgs
	roscpp
	rospy
	pluginlib
	cmake_modules
	geometric_shapes
	visualization_msgs
	vicon_bridge
)
set(Eigen_INCLUDE_DIRS "/usr/include/eigen3/Eigen/")
find_package(Boost REQUIRED system filesystem date_time thread)

catkin_package(
  INCLUDE_DIRS include
  CATKIN_DEPENDS
)
find_package(Eigen REQUIRED)

include_directories(
	include
  ${catkin_INCLUDE_DIRS}
)

add_executable(rviz_plotter src/rviz_plotter.cpp)
target_link_libraries(rviz_plotter ${catkin_LIBRARIES})
