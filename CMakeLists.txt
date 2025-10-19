cmake_minimum_required(VERSION 3.20)
project(NewSAGE)

list(APPEND CMAKE_MODULE_PATH ${PROJECT_SOURCE_DIR}/cmake)

include(FetchContent)

add_subdirectory(${PROJECT_SOURCE_DIR}/Compression)
