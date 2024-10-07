cmake_minimum_required(VERSION 3.10)
project(demo)

# CXX_STANDARD is depend on ROOT version
set(CMAKE_CXX_STANDARD 20)
set(CMAKE_CXX_STANDARD_REQUIRED True)

# set ROOT_DIR to the path of ROOT (optional)
if(NOT DEFINED ROOT_DIR)
    set(ROOT_DIR "/mnt/shared/Ubuntu/miniconda3/envs/ROOT")
endif()
message(STATUS "ROOT_DIR: ${ROOT_DIR}")

# set CMAKE_PREFIX_PATH to the path of ROOT (optional)
list(APPEND CMAKE_PREFIX_PATH ${ROOT_DIR})

find_package(ROOT REQUIRED)

# add ROOT include directories
include_directories(${ROOT_INCLUDE_DIRS})

# project settings
add_executable(main main.cpp)
target_link_libraries(main ${ROOT_LIBRARIES})