cmake_minimum_required(VERSION 3.1)

project(apue)

include_directories(${CMAKE_SOURCE_DIR}/include)

link_directories(${CMAKE_SOURCE_DIR}/lib)


#设置编译选项
set(CXX_FLAGS -g -Werror -O0)
# message(STATUS "CXX_FLAGS = ${CXX_FLAGS}")

# 设置C编译器的编译选项，CMAKE_CXX_FLAGS 是设置g++编译器的选项
# 或者也可以通过 add_compile_options()进行全局设置
string(REPLACE ";" " " CMAKE_C_FLAGS "${CXX_FLAGS}")
# message(STATUS ${CMAKE_CXX_FLAGS})



#指定静态库输出目录
set(LIBRARY_OUTPUT_DIRECTORY ${CMAKE_SOURCE_DIR}/lib)

#指定编译输出目录
set(EXECUTABLE_OUTPUT_PATH ${CMAKE_SOURCE_DIR}/bin)

add_subdirectory(${CMAKE_SOURCE_DIR}/lib)
add_subdirectory(${CMAKE_SOURCE_DIR}/src)