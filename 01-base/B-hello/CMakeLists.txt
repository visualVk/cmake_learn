cmake_minimum_required(VERSION 3.10)

project(hello_headers)

# set(SOURCES
# 	src/Hello.cpp
# 	src/main.cpp
# )

file(GLOB SOURCES "src/*.cpp")

add_executable(${PROJECT_NAME} ${SOURCES})

target_include_directories(${PROJECT_NAME}
	PRIVATE
		${PROJECT_SOURCE_DIR}/include
)
