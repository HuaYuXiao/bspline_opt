cmake_minimum_required(VERSION 2.8.3)
project(bspline_opt)

set(CMAKE_BUILD_TYPE "Release")
ADD_COMPILE_OPTIONS(-std=c++14 )
set(CMAKE_CXX_FLAGS "-std=c++14 ${CMAKE_CXX_FLAGS} -O3 -Wall")

set(CMAKE_PREFIX_PATH /opt/ros/noetic;/usr/local;$ENV{HOME}/planner_ws/devel;$ENV{HOME}/mapping_ws/devel;$ENV{HOME}/tool_ws/devel)
message(STATUS "CMAKE_PREFIX_PATH: ${CMAKE_PREFIX_PATH}")

find_package(Eigen3 REQUIRED)
find_package(PCL 1.7 REQUIRED)
find_package(catkin REQUIRED COMPONENTS
  roscpp
  rospy
  std_msgs
  visualization_msgs
  plan_env
        sdf_tools
        cv_bridge
        traj_utils
        path_searching
)

catkin_package(
 INCLUDE_DIRS include
 LIBRARIES bspline_opt
 CATKIN_DEPENDS plan_env
#  DEPENDS system_lib
)

include_directories( 
    SYSTEM 
    include 
    ${catkin_INCLUDE_DIRS}
    ${Eigen3_INCLUDE_DIRS} 
    ${PCL_INCLUDE_DIRS}
)

add_library(bspline_opt
        src/bspline_optimizer_fast.cpp
        src/bspline_optimizer_ego.cpp
    src/non_uniform_bspline.cpp
        src/uniform_bspline.cpp
        src/gradient_descent_optimizer.cpp
)
target_link_libraries( bspline_opt
    ${catkin_LIBRARIES}
    /usr/local/lib/libnlopt.so
    )  
