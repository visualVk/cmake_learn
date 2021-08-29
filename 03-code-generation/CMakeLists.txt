cmake_minimum_required(VERSION 3.5)

project(cf_example)

message(STATUS "${PROJECT_SOURCE_DIR}")
message(STATUS "${PROJECT_BINARY_DIR}")
message(STATUS "${CMAKE_SOURCE_DIR}")
message(STATUS "${CMAKE_BINARY_DIR}")


# set a project version
set (cf_example_VERSION_MAJOR 0)
set (cf_example_VERSION_MINOR 2)
set (cf_example_VERSION_PATCH 1)
set (cf_example_VERSION "${cf_example_VERSION_MAJOR}.${cf_example_VERSION_MINOR}.${cf_example_VERSION_PATCH}")

configure_file(ver.h.in ${PROJECT_SOURCE_DIR}/ver.h)
configure_file(path.h.in ${PROJECT_SOURCE_DIR}/path.h @ONLY)

add_executable(${PROJECT_NAME} main.cpp)

target_include_directories(${PROJECT_NAME} PUBLIC ${CMAKE_SOURCE_DIR})
