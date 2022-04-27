cmake_minimum_required(VERSION 3.6.3)
project(stockalert CXX)

set(CMAKE_CXX_STANDARD 11)

file(GLOB LIB_SOURCES src/*.cpp)
file(GLOB LIB_HEADERS src/*.hpp )
add_library(stockalert ${LIB_SOURCES} ${LIB_HEADERS})

add_executable(stock-alert src/main.cpp)
target_link_libraries(stock-alert stockalert curl)

enable_testing()
add_subdirectory(test)
