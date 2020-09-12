cmake_minimum_required(VERSION 3.0 FATAL_ERROR)

project(gtest-demo CXX)

# enable c++ 11
set(CMAKE_CXX_STANDARD 11)
set(CMAKE_CXX_STANDARD_REQUIRED True)

# take respectives flags for debug & release process 
set(CMAKE_CXX_FLAGS_DEBUG_INIT "-std=c++11 -fno-omit-frame-pointer")
set(CMAKE_CXX_FLAGS_RELEASE_INIT "-std=c++11 -g -O2")

# default build type : Debug
if (NOT CMAKE_BUILD_TYPE)
    set(CMAKE_BUILD_TYPE Debug)
endif()

# respective macro definitions
message("CMAKE_BUILD_TYPE = ${CMAKE_BUILD_TYPE}")
if(CMAKE_BUILD_TYPE MATCHES Debug)
    add_definitions("-D_DEBUG")
elseif(CMAKE_BUILD_TYPE MATCHES Release)
else()
endif()

add_subdirectory(src)

# CTest related
enable_testing()
add_subdirectory(tests)
