cmake_minimum_required(VERSION 3.1)

project(apue)

include_directories(${CMAKE_SOURCE_DIR}/include)

link_directories(${CMAKE_SOURCE_DIR}/lib)

#指定静态库输出目录
set(LIBRARY_OUTPUT_DIRECTORY ${CMAKE_SOURCE_DIR}/lib)

#指定编译输出目录
set(EXECUTABLE_OUTPUT_PATH ${CMAKE_SOURCE_DIR}/bin)

#设置编译选项
set(CXX_FLAGS -g -Werror -O0)
message(STATUS "CXX_FLAGS = ${CXX_FLAGS}")
string(REPLACE ";" " " CMAKE_CXX_FLAGS "${CXX_FLAGS}")

add_subdirectory(${CMAKE_SOURCE_DIR}/lib)
add_subdirectory(${CMAKE_SOURCE_DIR}/src)