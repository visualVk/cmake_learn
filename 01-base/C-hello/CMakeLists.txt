cmake_minimum_required(VERSION 3.5)
# 工程名
project(hello_library)
# 新建静态库（名称+STATIC+源文件）
add_library(hello_library STATIC src/Hello.cpp)
# 需要include的目录（名称+PUBLIC+目录）
target_include_directories(hello_library PUBLIC ${PROJECT_SOURCE_DIR}/include)
# 可执行文件（名称+依赖文件）
add_executable(hello_binary src/main.cpp)
# 关联依赖（名称+PRIVATE/PUBLIC+静态库）
target_link_libraries(hello_binary PRIVATE hello_library)
