project(NewSAGE.Compression.EAC)

list(
  APPEND
  HEADERS
  ${PROJECT_SOURCE_DIR}/include/NewSAGE/Compression/EAC/GIMEX.h
  ${PROJECT_SOURCE_DIR}/include/NewSAGE/Compression/EAC/Codex.h
  ${PROJECT_SOURCE_DIR}/include/NewSAGE/Compression/EAC/BTreeCodex.h
  ${PROJECT_SOURCE_DIR}/include/NewSAGE/Compression/EAC/HuffCodex.h
  ${PROJECT_SOURCE_DIR}/include/NewSAGE/Compression/EAC/RefCodex.h)

list(
  APPEND
  SOURCES
  ${PROJECT_SOURCE_DIR}/src/BTreeAbout.cpp
  ${PROJECT_SOURCE_DIR}/src/BTreeDecode.cpp
  ${PROJECT_SOURCE_DIR}/src/BTreeEncode.cpp
  ${PROJECT_SOURCE_DIR}/src/HuffAbout.cpp
  ${PROJECT_SOURCE_DIR}/src/HuffDecode.cpp
  ${PROJECT_SOURCE_DIR}/src/HuffEncode.cpp
  ${PROJECT_SOURCE_DIR}/src/RefAbout.cpp
  ${PROJECT_SOURCE_DIR}/src/RefDecode.cpp
  ${PROJECT_SOURCE_DIR}/src/RefEncode.cpp)

if(BUILD_SHARED_LIBS)
  add_library(${PROJECT_NAME} SHARED)
else()
  add_library(${PROJECT_NAME} STATIC)
endif()

target_sources(${PROJECT_NAME} PRIVATE ${SOURCES} ${HEADERS})

target_include_directories(${PROJECT_NAME} PUBLIC ${PROJECT_SOURCE_DIR}/include)

add_library(NewSAGE::Compression::EAC ALIAS ${PROJECT_NAME})
