cmake_minimum_required(VERSION 3.4)

project(libfranka-example CXX)
list(INSERT CMAKE_MODULE_PATH 0 "${CMAKE_CURRENT_SOURCE_DIR}/cmake")
set(CMAKE_CXX_STANDARD 14)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

find_package(Franka REQUIRED)
find_package(Eigen3 REQUIRED)

set(THREADS_PREFER_PTHREAD_FLAG ON)
find_package(Threads REQUIRED)

add_library(examples_common STATIC examples_common.cpp)
target_link_libraries(examples_common PUBLIC Franka::Franka Eigen3::Eigen3)

add_executable(pose_example pose_example.cpp)
target_link_libraries(pose_example Franka::Franka examples_common Eigen3::Eigen3)

