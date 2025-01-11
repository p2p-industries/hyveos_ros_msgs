cmake_minimum_required(VERSION 3.8)
project(hyveos_msgs)

if(CMAKE_COMPILER_IS_GNUCXX OR CMAKE_CXX_COMPILER_ID MATCHES "Clang")
  add_compile_options(-Wall -Wextra -Wpedantic)
endif()

# find dependencies
find_package(ament_cmake REQUIRED)
find_package(rosidl_default_generators REQUIRED)

set(msg_files
  "msg/ReceivedRequest.msg"
)

set(srv_files
  "srv/RequestSubscription.srv"
  "srv/Respond.srv"
  "srv/SendRequest.srv"
)

rosidl_generate_interfaces(${PROJECT_NAME}
  ${msg_files}
  ${srv_files}
)

ament_export_dependencies(rosidl_default_runtime)

ament_package()
