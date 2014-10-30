cmake_minimum_required(VERSION 2.8.4)
project(oash)

set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -std=c++11")

set(SOURCE_FILES src/main.cc)
add_executable(oash ${SOURCE_FILES})

add_subdirectory(lib/ext/googletest)
enable_testing()
include_directories(${gtest_SOURCE_DIR}/include ${gtest_SOURCE_DIR})

add_executable( runUnitTests test/sample.cc)
include_directories(src)
target_link_libraries(runUnitTests gtest gtest_main)