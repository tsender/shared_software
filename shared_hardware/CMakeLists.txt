cmake_minimum_required(VERSION 2.8.3)
project(shared_hardware)

find_package(catkin REQUIRED COMPONENTS roscpp roslint tf imu_3dm_gx4 sensor_msgs)

catkin_package()

roslint_cpp()

include_directories(${catkin_INCLUDE_DIRS})

add_executable(imu_state src/imu_state.cpp)
add_dependencies(imu_state imu_3dm_gx4_gencpp)
target_link_libraries(imu_state ${catkin_LIBRARIES})
