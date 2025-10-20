project(NewSAGE.Compression)

include(LZHL)
include(ZLib)

add_subdirectory(${PROJECT_SOURCE_DIR}/EAC)
add_subdirectory(${PROJECT_SOURCE_DIR}/LZHCompress)

list(APPEND HEADERS
     ${PROJECT_SOURCE_DIR}/include/NewSAGE/Compression/Compression.h)

list(APPEND SOURCES ${PROJECT_SOURCE_DIR}/src/CompressionManager.cpp)

if(BUILD_SHARED_LIBS)
  add_library(${PROJECT_NAME} SHARED)
else()
  add_library(${PROJECT_NAME} STATIC)
endif()

target_sources(${PROJECT_NAME} PRIVATE ${SOURCES} ${HEADERS})

target_include_directories(${PROJECT_NAME} PUBLIC ${PROJECT_SOURCE_DIR}/include)

target_link_libraries(
  ${PROJECT_NAME} PUBLIC NewSAGE::Compression::EAC
                         NewSAGE::Compression::LZHCompress ZLib)
