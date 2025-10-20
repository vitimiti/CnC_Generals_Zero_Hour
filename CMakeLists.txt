cmake_minimum_required(VERSION 3.20)
project(NewSAGE)

list(APPEND CMAKE_MODULE_PATH ${PROJECT_SOURCE_DIR}/cmake)

include(FetchContent)

list(APPEND HEADERS ${PROJECT_SOURCE_DIR}/include/NewSAGE/BaseType.h
     ${PROJECT_SOURCE_DIR}/include/NewSAGE/Trig.h)

list(APPEND COMMON_INCLUDE_DIRS ${PROJECT_SOURCE_DIR}/include)

add_subdirectory(${PROJECT_SOURCE_DIR}/Common)
add_subdirectory(${PROJECT_SOURCE_DIR}/Compression)
