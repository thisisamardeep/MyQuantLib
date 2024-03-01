cmake_minimum_required(VERSION 3.15.0)

# For MSVC RUNTIME LIBRARY, need CMP0091=NEW and cmake 3.15+
cmake_policy(SET CMP0091 NEW)
set(CMAKE_CXX_STANDARD 17)
SET(CMAKE_CXX_FLAGS "-save-temps -finstrument-functions -O0 -g3 -fno-elide-constructors")
set(CMAKE_VERBOSE_MAKEFILE ON)
SET(CMAKE_EXPORT_COMPILE_COMMANDS ON)
# Version info
set(QUANTLIB_VERSION_MAJOR 1)
set(QUANTLIB_VERSION_MINOR 34)
set(QUANTLIB_VERSION_PATCH 0)
set(QUANTLIB_VERSION ${QUANTLIB_VERSION_MAJOR}.${QUANTLIB_VERSION_MINOR}.${QUANTLIB_VERSION_PATCH})
set(PACKAGE_NAME          "MyQuantLib")

project(${PACKAGE_NAME} LANGUAGES CXX DESCRIPTION "The QuantLib C++ Library")

option(QL_BUILD_EXAMPLES "Build examples" ON)

add_subdirectory(ql)
if (QL_BUILD_EXAMPLES)
    add_subdirectory(Examples)
endif()