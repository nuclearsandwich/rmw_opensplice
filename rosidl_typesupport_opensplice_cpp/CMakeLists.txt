cmake_minimum_required(VERSION 2.8.3)

project(rosidl_typesupport_opensplice_cpp)

find_package(ament_cmake REQUIRED)
find_package(ament_cmake_environment_hooks REQUIRED)
find_package(ament_cmake_python REQUIRED)

find_package(opensplice REQUIRED COMPONENTS CXX)

ament_export_dependencies(rosidl_cmake)
ament_export_dependencies(rosidl_generator_dds_idl)

ament_environment_hooks(env_hook/opensplice.sh.in)

ament_python_install_package(${PROJECT_NAME})

ament_package(
  CONFIG_EXTRAS "rosidl_typesupport_opensplice_cpp-extras.cmake"
)

install(
  PROGRAMS bin/rosidl_typesupport_opensplice_cpp
  DESTINATION lib/rosidl_typesupport_opensplice_cpp
)
install(
  DIRECTORY cmake
  DESTINATION share/${PROJECT_NAME}
)