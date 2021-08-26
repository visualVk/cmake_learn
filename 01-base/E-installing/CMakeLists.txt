cmake_minimum_required(VERSION 3.5)

project(cmake_examples_install)

add_library(cmake_examples_inst SHARED src/Hello.cpp)

target_include_directories(cmake_examples_inst PUBLIC ${PROJECT_SOURCE_DIR}/include)

add_executable(cmake_examples_inst_bin src/main.cpp)

target_link_libraries(cmake_examples_inst_bin PRIVATE cmake_examples_inst)


# install
# binary
install(TARGETS cmake_examples_inst_bin DESTINATION bin)

# library
install (TARGETS cmake_examples_inst
    LIBRARY DESTINATION lib)

# header files
install(DIRECTORY ${PROJECT_SOURCE_DIR}/include/ DESTINATION include)

# config file
install(FILES cmake-exmpales.conf DESTINATION etc)
