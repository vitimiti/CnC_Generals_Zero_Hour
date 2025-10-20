project(NewSAGE.Common)

list(APPEND HEADERS ${PROJECT_SOURCE_DIR}/include/NewSAGE/Common/BaseType.h
     ${PROJECT_SOURCE_DIR}/include/NewSAGE/Common/Trig.h)

add_library(${PROJECT_NAME} INTERFACE)

# if(BUILD_SHARED_LIBS) add_library(${PROJECT_NAME} SHARED) else()
# add_library(${PROJECT_NAME} STATIC) endif()

target_sources(${PROJECT_NAME} INTERFACE ${HEADERS})

target_include_directories(${PROJECT_NAME}
                           INTERFACE ${PROJECT_SOURCE_DIR}/include)

add_library(NewSAGE::Common ALIAS ${PROJECT_NAME})
