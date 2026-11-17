cmake_minimum_required(VERSION 4.0)
project(CnC_Generals_Zero_Hour)

list(APPEND CMAKE_MODULE_PATH ${CMAKE_CURRENT_SOURCE_DIR}/cmake)

set(CMAKE_CXX_STANDARD 23)
set(CMAKE_CXX_STANDARD_REQUIRED ON)
set(CMAKE_CXX_EXTENSIONS OFF)
set(CMAKE_EXPORT_COMPILE_COMMANDS ON)

option(CNC_INTERNAL "Enable internal build" OFF)
option(CNC_REGENERATE_TRIG_TABLES "Regenerate the trigonometry tables" OFF)

message(STATUS "Configuring ${PROJECT_NAME}...")

if(CMAKE_BUILD_TYPE STREQUAL "Debug")
    add_definitions(-D_DEBUG)
endif()

if(CNC_INTERNAL)
    add_definitions(-D_INTERNAL)
endif()

add_subdirectory(Generals)

message(STATUS "Finished configuring ${PROJECT_NAME}")
