cmake_minimum_required(VERSION 3.10)

# Project name and version
project(graph_problem VERSION 1.0)

# Set the C++ standard
set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED True)

# set(CMAKE_BUILD_TYPE Debug)
set(CMAKE_BUILD_TYPE Release)

# Set the default build type to Release if not specified
if(NOT CMAKE_BUILD_TYPE)
    set(CMAKE_BUILD_TYPE "Release" CACHE STRING "Choose the type of build." FORCE)
endif()

# Find OpenCV package
find_package(OpenCV REQUIRED)

# Add the executable
add_executable(example example.cpp)

# Link OpenMP and OpenCV libraries
target_link_libraries(example ${OpenCV_LIBS})