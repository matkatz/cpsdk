cmake_minimum_required(VERSION 3.1.0)

project(cp_sdk)

option(BUILD_SHARED_LIBS "Build shared library" ON)

add_subdirectory(cpl)
add_subdirectory(examples)
