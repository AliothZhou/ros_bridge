cmake_minimum_required(VERSION 3.0.2)
project(bridge_interfaces)

catkin_package(

  # INCLUDE_DIRS include
  # LIBRARIES bridge_interfaces
  # CATKIN_DEPENDS roscpp std_msgs
  # DEPENDS system_lib
)

include_directories(

  # include
  ${catkin_INCLUDE_DIRS}
)
