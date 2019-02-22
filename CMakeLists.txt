cmake_minimum_required(VERSION 3.0)

##
## PROJECT
## name and version
##
project(ANN VERSION 1.1.2 LANGUAGES CXX)

##
## OPTIONS
##
option(ANN_BuildTests "Build tests." ON)

##
## INCLUDE  DIRs
##
#
include_directories(${CMAKE_CURRENT_SOURCE_DIR}/include)


set(PROJECT_BINARY_DIR ${CMAKE_CURRENT_SOURCE_DIR}/bin)
set(PROJECT_LIB_DIR ${CMAKE_CURRENT_SOURCE_DIR}/lib)

add_subdirectory(src)
add_subdirectory(sample)
add_subdirectory(ann2fig)

if (ANN_BuildTests)
    message(STATUS "Building tests is enabled")
    enable_testing()
    add_subdirectory(test)
endif()






