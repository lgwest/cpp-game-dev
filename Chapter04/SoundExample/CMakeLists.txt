cmake_minimum_required(VERSION 3.0)

project(SoundExample)

set(SOURCES 
App.cpp
App.h
GamePlayScreen.cpp
GamePlayScreen.h
Main.cpp
)

include_directories(${CH04_DIR})
include_directories(${CH04_DIR}/include)
link_directories(${CMAKE_CURRENT_BINARY_DIR})
link_directories(${CH04_DIR}/lib/Windows/x86)


add_executable(SoundExample ${SOURCES})

target_link_libraries(SoundExample debug BookEngine)
target_link_libraries(SoundExample optimized BookEngine)

file(COPY "${CMAKE_CURRENT_SOURCE_DIR}/lib/Windows/x86/Debug/" DESTINATION "${CMAKE_CURRENT_BINARY_DIR}/Debug/" FILES_MATCHING PATTERN "*.dll")
file(COPY "${CMAKE_CURRENT_SOURCE_DIR}/BookEngine/Debug/" DESTINATION "${CMAKE_CURRENT_BINARY_DIR}/Debug/" FILES_MATCHING PATTERN "*.dll")

file(COPY "${CMAKE_CURRENT_SOURCE_DIR}/lib/Windows/x86/Release/" DESTINATION "${CMAKE_CURRENT_BINARY_DIR}/Release/" FILES_MATCHING PATTERN "*.dll")
file(COPY "${CMAKE_CURRENT_SOURCE_DIR}/BookEngine/Release/" DESTINATION "${CMAKE_CURRENT_BINARY_DIR}/Release/" FILES_MATCHING PATTERN "*.dll")

file(COPY "${CMAKE_CURRENT_SOURCE_DIR}/Audio" DESTINATION "${CMAKE_CURRENT_BINARY_DIR}")
#file(COPY "${CMAKE_CURRENT_SOURCE_DIR}/Audio/" DESTINATION "${CMAKE_CURRENT_BINARY_DIR}/Release/")


