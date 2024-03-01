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
set(PACKAGE_VERSION       "${QUANTLIB_VERSION}-dev")
set(PACKAGE_VERSION_HEX   "0x01340000")
set(PACKAGE_STRING        "${PACKAGE_NAME} ${PACKAGE_VERSION}")
set(PACKAGE_TARNAME       "${PACKAGE_NAME}-${PACKAGE_VERSION}")
set(PACKAGE_BUGREPORT     "https://github.com/lballabio/QuantLib/issues/")


# Default build type for single-config generators (set this before project() command)
# For multi-config generators, such as Visual Studio, use: cmake --build . --config=<CONFIG>
if (NOT CMAKE_BUILD_TYPE OR CMAKE_BUILD_TYPE STREQUAL "")
    set(CMAKE_BUILD_TYPE "Release" CACHE
            STRING "Build type for single-config generators" FORCE)
endif()


project(${PACKAGE_NAME} LANGUAGES CXX DESCRIPTION "The QuantLib C++ Library")













option(QL_BUILD_EXAMPLES "Build examples" ON)



set(QL_HAVE_CONFIG_H ON)
set(QL_VERSION ${PACKAGE_VERSION})
set(QL_HEX_VERSION ${PACKAGE_VERSION_HEX})
configure_file(ql/config.hpp.cfg ql/config.hpp @ONLY)



add_subdirectory(ql)
if (QL_BUILD_EXAMPLES)
    add_subdirectory(Examples)
endif()
