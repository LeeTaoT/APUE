cmake_minimum_required(VERSION 3.1)

file( GLOB APP_SOURCE RELATIVE ${CMAKE_CURRENT_SOURCE_DIR} *.c )

foreach(APP_NAME ${APP_SOURCE})
	get_filename_component(APP ${APP_NAME} NAME_WE)
	link_libraries(myapuelib)
	message(STATUS "APP = ${APP}")
	add_executable(${APP} ${APP_NAME})
endforeach(APP_NAME ${APP_SOURCE})

