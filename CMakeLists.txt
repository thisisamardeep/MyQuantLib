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

# Path for package-local cmake modules
set(CMAKE_MODULE_PATH "${PROJECT_SOURCE_DIR}/cmake" ${CMAKE_MODULE_PATH})

# Installation directories
set(QL_INSTALL_BINDIR "bin" CACHE STRING "Installation directory for executables")
set(QL_INSTALL_LIBDIR "lib" CACHE STRING "Installation directory for libraries")
set(QL_INSTALL_INCLUDEDIR "include" CACHE STRING "Installation directory for headers")
set(QL_INSTALL_EXAMPLESDIR "lib/QuantLib/examples" CACHE STRING
        "Installation directory for examples")
set(QL_INSTALL_CMAKEDIR "lib/cmake/${PACKAGE_NAME}" CACHE STRING
        "Installation directory for CMake scripts")







option(QL_BUILD_BENCHMARK "Build benchmark" OFF)
option(QL_BUILD_EXAMPLES "Build examples" OFF)
option(QL_BUILD_TEST_SUITE "Build test suite" OFF)
option(QL_BUILD_FUZZ_TEST_SUITE "Build fuzz test suite" OFF)
option(QL_ENABLE_OPENMP "Detect and use OpenMP" OFF)
option(QL_ENABLE_PARALLEL_UNIT_TEST_RUNNER "Enable the parallel unit test runner" OFF)
option(QL_ENABLE_SESSIONS "Singletons return different instances for different sessions" OFF)
option(QL_ENABLE_THREAD_SAFE_OBSERVER_PATTERN "Enable the thread-safe observer pattern" OFF)
option(QL_ENABLE_TRACING "Tracing messages should be allowed" OFF)
option(QL_ENABLE_DEFAULT_WARNING_LEVEL "Enable the default warning level to pass the ci pipeline" ON)
option(QL_COMPILE_WARNING_AS_ERROR "Specify whether to treat warnings on compile as errors." OFF)
option(QL_ERROR_FUNCTIONS "Error messages should include current function information" OFF)
option(QL_ERROR_LINES "Error messages should include file and line information" OFF)
option(QL_EXTRA_SAFETY_CHECKS "Extra safety checks should be performed" OFF)
option(QL_HIGH_RESOLUTION_DATE "Enable date resolution down to microseconds" OFF)
option(QL_THROW_IN_CYCLES "Throw an exception when a notification loop is detected" OFF)
option(QL_FASTER_LAZY_OBJECTS "Cause lazy objects to forward just the first notification instead of every one" ON)
option(QL_NULL_AS_FUNCTIONS "Enable the implementation of Null as template functions" OFF)
option(QL_INSTALL_BENCHMARK "Install benchmark" ON)
option(QL_INSTALL_EXAMPLES "Install examples" ON)
option(QL_INSTALL_TEST_SUITE "Install test suite" ON)
option(QL_TAGGED_LAYOUT "Library names use layout tags" ${MSVC})
option(QL_USE_CLANG_TIDY "Use clang-tidy when building" OFF)
option(QL_USE_INDEXED_COUPON "Use indexed coupons instead of par coupons" OFF)
option(QL_USE_STD_ANY "Use std::any instead of boost::any" ON)
option(QL_USE_STD_CLASSES "Enable all QL_USE_STD_ options" ON)
option(QL_USE_STD_FUNCTION "Use std::function and std::bind instead of Boost ones" ON)
option(QL_USE_STD_OPTIONAL "Use std::optional instead of boost::optional" ON)
option(QL_USE_STD_SHARED_PTR "Use standard smart pointers instead of Boost ones" ON)
option(QL_USE_STD_TUPLE "Use std::tuple instead of boost::tuple" ON)
set(QL_EXTERNAL_SUBDIRECTORIES "" CACHE STRING "Optional list of external source directories to be added to the build (semicolon-separated)")
set(QL_EXTRA_LINK_LIBRARIES "" CACHE STRING "Optional extra link libraries to add to QuantLib")



set(QL_HAVE_CONFIG_H ON)
set(QL_VERSION ${PACKAGE_VERSION})
set(QL_HEX_VERSION ${PACKAGE_VERSION_HEX})
configure_file(ql/config.hpp.cfg ql/config.hpp @ONLY)
configure_file(ql/qldefines.hpp.cfg ql/qldefines.hpp @ONLY)

function(getAllSubdirs dir dirs)
    # get subdirectories for dir
    get_property(subdirs DIRECTORY ${dir} PROPERTY SUBDIRECTORIES)
    # iterate any found subdirectories
    foreach(subdir ${subdirs})
        # append each sub directory
        list(APPEND ${dirs} "\n" ${subdir})
        getAllSubdirs(${subdir} ${dirs})
    endforeach()
    set(${dirs} ${${dirs}} PARENT_SCOPE)
endfunction()



add_subdirectory(ql)
if (QL_BUILD_EXAMPLES)
    add_subdirectory(Examples)
endif()


if (QL_BUILD_EXAMPLES)
    add_subdirectory(Examples)
endif()
if (QL_BUILD_TEST_SUITE OR QL_BUILD_BENCHMARK)
    add_subdirectory(test-suite)
endif()

if ('${CMAKE_CXX_COMPILER_ID}' MATCHES 'Clang' AND  QL_BUILD_FUZZ_TEST_SUITE)
    add_subdirectory(fuzz-test-suite)
endif()






set(Project_Directories ${CMAKE_SOURCE_DIR})
getAllSubDirs(. Project_Directories)
message("all dirs " ${Project_Directories})

function(print_all_targets DIR)
    get_property(TGTS DIRECTORY "${DIR}" PROPERTY BUILDSYSTEM_TARGETS)
    foreach(TGT IN LISTS TGTS)
        message(STATUS "Target: ${TGT}")
        # TODO: Do something about it
    endforeach()

    get_property(SUBDIRS DIRECTORY "${DIR}" PROPERTY SUBDIRECTORIES)
    foreach(SUBDIR IN LISTS SUBDIRS)
        print_all_targets("${SUBDIR}")
    endforeach()
endfunction()

print_all_targets(.)