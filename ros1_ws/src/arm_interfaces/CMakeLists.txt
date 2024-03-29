cmake_minimum_required(VERSION 3.0.2)
project(arm_interfaces)

find_package(catkin REQUIRED COMPONENTS
  roscpp
  std_msgs
  geometry_msgs
  message_generation
)

add_service_files(
  FILES
  WalkerMotion.srv
)

generate_messages(
  DEPENDENCIES
  std_msgs
  geometry_msgs
)
catkin_package(
)

include_directories(
  ${catkin_INCLUDE_DIRS}
)
