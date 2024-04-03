cmake_minimum_required(VERSION 3.1)
project(add LANGUAGES CXX)

# Set the output folder where your program will be created
set(CMAKE_BINARY_DIR ${CMAKE_SOURCE_DIR}/bin)
set(EXECUTABLE_OUTPUT_PATH ${CMAKE_BINARY_DIR})
set(LIBRARY_OUTPUT_PATH ${CMAKE_BINARY_DIR})

add_library(
	mylibs SHARED #STATIC
	hello.cpp
	hello.h
)

add_executable(add main.cpp)
target_link_libraries(add
	mylibs
)
