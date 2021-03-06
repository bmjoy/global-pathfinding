cmake_minimum_required(VERSION 2.8)

set(CMAKE_C_COMPILER "clang")
set(CMAKE_CXX_COMPILER "clang++")

project(global_pathfinding CXX)

set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -std=c++14 -Wall -Wextra")
set(CMAKE_CXX_FLAGS_RELEASE "${CMAKE_CXX_FLAGS_RELEASE} -O3")

set(CMAKE_ARCHIVE_OUTPUT_DIRECTORY ${CMAKE_BINARY_DIR}/lib)
set(CMAKE_LIBRARY_OUTPUT_DIRECTORY ${CMAKE_BINARY_DIR}/lib)
set(CMAKE_RUNTIME_OUTPUT_DIRECTORY ${CMAKE_BINARY_DIR}/bin)

############
# INCLUDES #
############

# Include libraries
include(lib/core_libs.cmake)

#########
# FLAGS #
#########

# Define the command-line flags that should be accessible to programs
option(SAILBOT_DEBUG "Whether to build the project with the SAILBOT_DEBUG variable defined at the preprocessor level" OFF)
if(SAILBOT_DEBUG)
    add_definitions(-DSAILBOT_DEBUG)
endif()

############
# PROGRAMS #
############

# Include library files to avoid ugly relative paths
include_directories(src)

# Add main library
add_subdirectory(src)

# Add projects (all executables)
add_subdirectory(projects)

# Add tests
add_subdirectory(test)
