cmake_minimum_required(VERSION 3.0.2)
project(vision_interfaces)

find_package(catkin REQUIRED COMPONENTS
  roscpp
  std_msgs
  sensor_msgs
  geometry_msgs
  message_generation
)

add_message_files(
  FILES
  Grasp2DInfo.msg
  Grasp6DInfo.msg
  Grasp6DPoint.msg
  Grasp2D.msg
  Grasp6D.msg
)

generate_messages(
  DEPENDENCIES
  std_msgs
  sensor_msgs
  geometry_msgs
)

catkin_package(
)

include_directories(
  ${catkin_INCLUDE_DIRS}
)
