cmake_minimum_required(VERSION 2.8.3)
project(ranger_rf)

add_compile_options(-std=c++11)
find_package(catkin REQUIRED COMPONENTS
  roscpp
  roslib
)

catkin_package(
#  INCLUDE_DIRS include
#  LIBRARIES val_desc
#  CATKIN_DEPENDS other_catkin_pkg
#  DEPENDS system_lib
)

## ======================================================================================##
## Subdirectories and source files
## ======================================================================================##
include_directories(cpp_version/src cpp_version/src/utility cpp_version/src/Forest cpp_version/src/Tree)
file(GLOB_RECURSE SOURCES cpp_version/src/*.cpp)

## ======================================================================================##
## Executable
## ======================================================================================##
add_executable(ranger ${SOURCES})
target_link_libraries(ranger ${catkin_LIBRARIES})