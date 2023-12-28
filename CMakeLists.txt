cmake_minimum_required(VERSION 3.12)

project(cm-config-file)

string(TIMESTAMP BUILD_TIME_YEAR %y)
string(TIMESTAMP BUILD_TIME_MONTH %m)
string(TIMESTAMP BUILD_TIME_DAY %d)

set(BUILD_AUTHOR "sdc")

set(DEBUG_LEVEL 1 CACHE STRING "debug level")

option(MEM_CHECKER "check memory malloc and free" ON)

#使用cmakelist的变量的第一种方法
configure_file (${CMAKE_CURRENT_LIST_DIR}/config.h.in ${CMAKE_CURRENT_BINARY_DIR}/config.h)

include_directories(${CMAKE_CURRENT_BINARY_DIR})

#使用cmakelist的变量的第二种方法
set(BUILD_USER "OSWIN")
add_definitions("-DBUILD_USER=\"${BUILD_USER}\"")

add_executable(${PROJECT_NAME} main.c)

