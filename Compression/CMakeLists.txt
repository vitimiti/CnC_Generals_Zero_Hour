project(NewSAGE.Compression)

include(lzhl)
include(zlib)

add_subdirectory(${PROJECT_SOURCE_DIR}/EAC)
add_subdirectory(${PROJECT_SOURCE_DIR}/LZHCompress)
