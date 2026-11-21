cmake_minimum_required(VERSION 4.0)
project(CnC_Generals_Zero_Hour)

list(APPEND CMAKE_MODULE_PATH ${CMAKE_CURRENT_SOURCE_DIR}/cmake)

set(CMAKE_CXX_STANDARD 23)
set(CMAKE_CXX_STANDARD_REQUIRED ON)
set(CMAKE_CXX_EXTENSIONS OFF)
set(CMAKE_EXPORT_COMPILE_COMMANDS ON)

option(CNC_BUILD_GENERALS "Build the Generals module" ON)
option(CNC_INTERNAL "Enable internal build" OFF)

message(STATUS "Configuring ${PROJECT_NAME}...")

if(CMAKE_BUILD_TYPE STREQUAL "Debug")
    add_definitions(-D_DEBUG)
endif()

# Only one of INTERNAL or DEBUG!
if(CNC_INTERNAL AND NOT CMAKE_BUILD_TYPE STREQUAL "Debug")
    add_definitions(-D_INTERNAL)
endif()

# This is mandatory with the GPL licensing requirements
set(BUILD_SHARED_LIBS ON)

include(cmake/FetchSDL.cmake)

if(CNC_BUILD_GENERALS)
    add_subdirectory(Generals)
endif()

message(STATUS "Finished configuring ${PROJECT_NAME}")
