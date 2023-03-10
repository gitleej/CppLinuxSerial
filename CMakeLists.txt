cmake_minimum_required(VERSION 3.1.0)
project(CppLinuxSerial)

add_definitions(-std=c++11)
set(CMAKE_CXX_STANDARD 11)
set(CMAKE_CXX_STANDARD_REQUIRED ON)
set(CMAKE_CXX_EXTENSIONS OFF)

file(GLOB_RECURSE CppLinuxSerial_SRC
        "*.cpp")

file(GLOB_RECURSE CppLinuxSerial_HEADERS
        "${CMAKE_SOURCE_DIR}/include/*.hpp")

option(SERIAL_BUILD_SHARED_LIBS "Build CppLinuxSerial shared library" OFF)

if (SERIAL_BUILD_SHARED_LIBS)
  set(LibType SHARED)
else()
  set(LibType STATIC)
endif()

add_library(CppLinuxSerial ${LibType} ${CppLinuxSerial_SRC} ${CppLinuxSerial_HEADERS})
