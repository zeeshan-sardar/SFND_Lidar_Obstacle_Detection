cmake_minimum_required(VERSION 2.8 FATAL_ERROR)

add_definitions(-std=c++14)

set(CXX_FLAGS "-Wall")
set(CMAKE_CXX_FLAGS, "${CXX_FLAGS}")
set(CMAKE_C_COMPILER "/usr/bin/gcc-9")
set(CMAKE_CXX_COMPILER "/usr/bin/g++-9")

project(playback)

find_package(PCL 1.2 REQUIRED)

include_directories(${PCL_INCLUDE_DIRS})
link_directories(${PCL_LIBRARY_DIRS})
add_definitions(${PCL_DEFINITIONS})
list(REMOVE_ITEM PCL_LIBRARIES "vtkproj4")


add_executable (quizRansac ransac2d.cpp ../../render/render.cpp)
target_link_libraries (quizRansac ${PCL_LIBRARIES})




