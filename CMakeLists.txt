cmake_minimum_required(VERSION 3.14)

project(cradle-vcpkg-starter)

# TODO: This should be inherited properly from CRADLE.
set(CMAKE_CXX_STANDARD 20)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

find_package(cradle REQUIRED)

add_executable(app main.cpp)
target_link_libraries(app cradle::cradle)
