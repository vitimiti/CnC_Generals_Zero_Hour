project(NewSAGE.Compression.LZHCompress)

list(
  APPEND HEADERS
  ${PROJECT_SOURCE_DIR}/include/NewSAGE/Compression/LZHCompress/NOXCompress.h)

list(APPEND SOURCES ${PROJECT_SOURCE_DIR}/src/NOXCompress.cpp)

if(BUILD_SHARED_LIBS)
  add_library(${PROJECT_NAME} SHARED)
else()
  add_library(${PROJECT_NAME} STATIC)
endif()

target_sources(${PROJECT_NAME} PRIVATE ${SOURCES} ${HEADERS})

target_include_directories(${PROJECT_NAME} PUBLIC ${PROJECT_SOURCE_DIR}/include)

# Link the NewSAGE interface target so its include directories and usage
# requirements propagate to this target. Do not pass the target name as a
# literal path to target_include_directories.
target_link_libraries(${PROJECT_NAME} PUBLIC liblzhl NewSAGE)
