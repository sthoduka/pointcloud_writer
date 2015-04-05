cmake_minimum_required(VERSION 2.8.3)
project(pointcloud_writer)

find_package(catkin REQUIRED
  COMPONENTS
    roscpp
)
find_package(PCL 1.7 REQUIRED)

catkin_package()

include_directories(
  ros/include
  ${catkin_INCLUDE_DIRS}
  ${PCL_INCLUDE_DIRS}
)

### EXECUTABLES ###############################################
add_executable(pointcloud_writer
  ros/src/pointcloud_writer_node.cpp
)
target_link_libraries(pointcloud_writer
  ${catkin_LIBRARIES}
  ${PCL_LIBRARIES}
)
