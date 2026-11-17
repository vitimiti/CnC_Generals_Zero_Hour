project(Generals_GameEngine)

message(STATUS "Configuring ${PROJECT_NAME}...")

if(CNC_REGENERATE_TRIG_TABLES)
    add_definitions(-DREGENERATE_TRIG_TABLES)
endif()

add_library(${PROJECT_NAME} STATIC)
add_library(Generals::GameEngine ALIAS ${PROJECT_NAME})

target_sources(
    ${PROJECT_NAME}
    PRIVATE ${PROJECT_SOURCE_DIR}/Source/Common/System/Trig.cpp
)

target_link_libraries(${PROJECT_NAME} PUBLIC Generals::Libraries)

target_include_directories(${PROJECT_NAME} PUBLIC ${PROJECT_SOURCE_DIR}/Include)

message(STATUS "Finished configuring ${PROJECT_NAME}")
