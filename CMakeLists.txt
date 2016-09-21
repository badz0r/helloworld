cmake_minimum_required (VERSION 2.8)
project HelloWorld

# The version number.
set (HelloWorld_VERSION_MAJOR 1)
set (HelloWorld_VERSION_MINOR 0)

// the configured options and settings for HelloWorld
#define HelloWorld_VERSION_MAJOR @HelloWorld_VERSION_MAJOR@
#define HelloWorld_VERSION_MINOR @HelloWorld_VERSION_MINOR@

# configure a header file to pass some of the CMake settings
# to the source code
set(RESOURCES_PATH "${PROJECT_SOURCE_DIR}/resources/")
configure_file (
  "${PROJECT_SOURCE_DIR}/HelloWorldCMakeConfig.h.in"
  "${PROJECT_BINARY_DIR}/HelloWorldCMakeConfig.h"
  )
 
# add the binary tree to the search path for include files
# so that we will find HelloWorldCMakeConfig.h
include_directories("${PROJECT_BINARY_DIR}")
 
# add the executable
add_executable(HelloWorld HelloWorld/HelloWorld.cpp HelloWorld/stdafx.cpp)

# does the application run
# add_test (HelloWorldRuns Test)