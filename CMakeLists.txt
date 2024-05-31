cmake_minimum_required(VERSION 2.8.3)
project(bspline_opt)

set(CMAKE_BUILD_TYPE "Release")
ADD_COMPILE_OPTIONS(-std=c++14)
set(CMAKE_CXX_FLAGS "-std=c++14 ${CMAKE_CXX_FLAGS} -O3 -Wall")
message(STATUS "CMAKE_PREFIX_PATH: ${CMAKE_PREFIX_PATH}")

find_package(Eigen3 REQUIRED)
find_package(PCL 1.7 REQUIRED)
find_package(catkin REQUIRED COMPONENTS
  roscpp
  rospy
  std_msgs
  visualization_msgs
  plan_env
        cv_bridge
        path_searching
)

catkin_package(
 INCLUDE_DIRS include
 LIBRARIES ${PROJECT_NAME}
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

add_library(${PROJECT_NAME}
        src/bspline_optimizer_fast.cpp
    src/non_uniform_bspline.cpp
        src/bspline_optimizer_ego.cpp
        src/uniform_bspline.cpp
        src/gradient_descent_optimizer.cpp
        src/bspline_optimizer_pe.cpp
)
target_link_libraries(${PROJECT_NAME}
    ${catkin_LIBRARIES}
    /usr/local/lib/libnlopt.so
)
