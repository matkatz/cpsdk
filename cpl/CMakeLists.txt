cmake_minimum_required(VERSION 3.1.0)

project(cpl)

set(CPL_TARGET ${PROJECT_NAME})
    
if(BUILD_SHARED_LIBS)
    add_library(${CPL_TARGET} SHARED "")
else()
    add_library(${CPL_TARGET} STATIC "")
endif()

# Enable C++11
set(CMAKE_CXX_STANDARD 11)
set(CMAKE_CXX_STANDARD_REQUIRED TRUE)

include(include/CMakeLists.txt)
include(src/CMakeLists.txt)

set_target_properties(${CPL_TARGET}
    PROPERTIES
    ARCHIVE_OUTPUT_DIRECTORY "${CMAKE_BINARY_DIR}/lib"
    LIBRARY_OUTPUT_DIRECTORY "${CMAKE_BINARY_DIR}/lib"
    RUNTIME_OUTPUT_DIRECTORY "${CMAKE_BINARY_DIR}/bin"
)
