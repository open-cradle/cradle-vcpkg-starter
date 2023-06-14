cmake_minimum_required(VERSION 3.14)

# Set VCPKG target triplet to use our mixed-linkage build.
if (WIN32)
    # This assumes we're doing a 64-bit build. It seems impossible to verify
    # that at this point in the CMake execution - it's possible after the call
    # to `project()`, but we need to set these variables before that - but we
    # could add an option to support 32-bit builds.
    set(VCPKG_TARGET_TRIPLET x64-windows-mixed)
    set(VCPKG_HOST_TRIPLET x64-windows-mixed)
endif()

project(cradle-vcpkg-starter)

# TODO: This should be inherited properly from CRADLE.
set(CMAKE_CXX_STANDARD 20)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

find_package(cradle REQUIRED)

add_executable(app main.cpp)
target_link_libraries(app cradle::cradle)
