cmake_minimum_required(VERSION 3.5)
project(vision_interfaces)

# Default to C99
if(NOT CMAKE_C_STANDARD)
  set(CMAKE_C_STANDARD 99)
endif()

# Default to C++17
if(NOT CMAKE_CXX_STANDARD)
  set(CMAKE_CXX_STANDARD 17)
endif()

if(CMAKE_COMPILER_IS_GNUCXX OR CMAKE_CXX_COMPILER_ID MATCHES "Clang")
  add_compile_options(-Wall -Wextra -Wpedantic)
endif()

# find dependencies
find_package(ament_cmake REQUIRED)
find_package(rosidl_default_generators REQUIRED)
find_package(builtin_interfaces REQUIRED)
find_package(geometry_msgs REQUIRED)
find_package(sensor_msgs REQUIRED)

# set(action_files
# )
set(msg_files
  "msg/Grasp6DPoint.msg"
  "msg/Grasp6DInfo.msg"
  "msg/Grasp2DInfo.msg"
  "msg/Grasp6D.msg"
  "msg/Grasp2D.msg"
)

rosidl_generate_interfaces(${PROJECT_NAME}
  ${msg_files}

  # ${action_files}
  DEPENDENCIES
  builtin_interfaces
  geometry_msgs
  sensor_msgs

  # std_msgs
  # trajectory_msgs
  # industrial_msgs
)

ament_export_dependencies(rosidl_default_runtime)
ament_export_include_directories(include)

ament_package()
