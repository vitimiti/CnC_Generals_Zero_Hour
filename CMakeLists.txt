cmake_minimum_required(VERSION 3.20)
project(NewSAGE)

list(APPEND CMAKE_MODULE_PATH ${PROJECT_SOURCE_DIR}/cmake)

include(FetchContent)

list(APPEND HEADERS ${PROJECT_SOURCE_DIR}/include/NewSAGE/BaseType.h
     ${PROJECT_SOURCE_DIR}/include/NewSAGE/Trig.h)

add_library(${PROJECT_NAME} INTERFACE)

target_include_directories(${PROJECT_NAME}
                           INTERFACE ${PROJECT_SOURCE_DIR}/include)

target_sources(${PROJECT_NAME} INTERFACE ${HEADERS})

add_subdirectory(${PROJECT_SOURCE_DIR}/Compression)
