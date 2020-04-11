cmake_minimum_required(VERSION 3.0)

project(ExampleCode04)

set(CHAP_SRC_DIR ${CMAKE_CURRENT_SOURCE_DIR})
set(CHAP_BIN_DIR ${CMAKE_CURRENT_BINARY_DIR})

message("CHAP_SRC_DIR is ${CHAP_SRC_DIR}")
message("CHAP_BIN_DIR is ${CHAP_BIN_DIR}")

add_subdirectory(BookEngine)
add_subdirectory(TextureExample)
add_subdirectory(ModelExample)
add_subdirectory(SoundExample)

