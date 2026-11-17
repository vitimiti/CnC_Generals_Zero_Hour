project(Generals_Libraries)

message(STATUS "Configuring ${PROJECT_NAME}...")

add_library(${PROJECT_NAME} INTERFACE)
add_library(Generals::Libraries ALIAS ${PROJECT_NAME})

target_sources(
    ${PROJECT_NAME}
    INTERFACE
        ${PROJECT_SOURCE_DIR}/Include/Lib/Trig.h
        ${PROJECT_SOURCE_DIR}/Include/Lib/BaseType.h
)

target_include_directories(
    ${PROJECT_NAME}
    INTERFACE ${PROJECT_SOURCE_DIR}/Include
)

message(STATUS "Finished configuring ${PROJECT_NAME}")
