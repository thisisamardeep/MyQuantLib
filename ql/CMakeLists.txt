set(QL_SOURCES
    instruments/vanillaswap.cpp
)

set(QL_HEADERS
    instruments/vanillaswap.hpp
)

set(QL_CONFIGURED_HEADERS
    ${PROJECT_BINARY_DIR}/ql/config.hpp
    ${PROJECT_BINARY_DIR}/ql/qldefines.hpp)

set(QL_GENERATED_HEADERS
    ${PROJECT_BINARY_DIR}/ql/quantlib.hpp
    ${PROJECT_BINARY_DIR}/ql/cashflows/all.hpp
    ${PROJECT_BINARY_DIR}/ql/currencies/all.hpp
    ${PROJECT_BINARY_DIR}/ql/experimental/all.hpp
    ${PROJECT_BINARY_DIR}/ql/experimental/asian/all.hpp
    ${PROJECT_BINARY_DIR}/ql/experimental/averageois/all.hpp
    ${PROJECT_BINARY_DIR}/ql/experimental/barrieroption/all.hpp
    ${PROJECT_BINARY_DIR}/ql/experimental/basismodels/all.hpp
    ${PROJECT_BINARY_DIR}/ql/experimental/callablebonds/all.hpp
    ${PROJECT_BINARY_DIR}/ql/experimental/catbonds/all.hpp
    ${PROJECT_BINARY_DIR}/ql/experimental/commodities/all.hpp
    ${PROJECT_BINARY_DIR}/ql/experimental/coupons/all.hpp
    ${PROJECT_BINARY_DIR}/ql/experimental/credit/all.hpp
    ${PROJECT_BINARY_DIR}/ql/experimental/exoticoptions/all.hpp
    ${PROJECT_BINARY_DIR}/ql/experimental/finitedifferences/all.hpp
    ${PROJECT_BINARY_DIR}/ql/experimental/forward/all.hpp
    ${PROJECT_BINARY_DIR}/ql/experimental/fx/all.hpp
    ${PROJECT_BINARY_DIR}/ql/experimental/inflation/all.hpp
    ${PROJECT_BINARY_DIR}/ql/experimental/lattices/all.hpp
    ${PROJECT_BINARY_DIR}/ql/experimental/math/all.hpp
    ${PROJECT_BINARY_DIR}/ql/experimental/mcbasket/all.hpp
    ${PROJECT_BINARY_DIR}/ql/experimental/models/all.hpp
    ${PROJECT_BINARY_DIR}/ql/experimental/processes/all.hpp
    ${PROJECT_BINARY_DIR}/ql/experimental/risk/all.hpp
    ${PROJECT_BINARY_DIR}/ql/experimental/shortrate/all.hpp
    ${PROJECT_BINARY_DIR}/ql/experimental/swaptions/all.hpp
    ${PROJECT_BINARY_DIR}/ql/experimental/termstructures/all.hpp
    ${PROJECT_BINARY_DIR}/ql/experimental/variancegamma/all.hpp
    ${PROJECT_BINARY_DIR}/ql/experimental/varianceoption/all.hpp
    ${PROJECT_BINARY_DIR}/ql/experimental/volatility/all.hpp
    ${PROJECT_BINARY_DIR}/ql/indexes/all.hpp
    ${PROJECT_BINARY_DIR}/ql/indexes/ibor/all.hpp
    ${PROJECT_BINARY_DIR}/ql/indexes/inflation/all.hpp
    ${PROJECT_BINARY_DIR}/ql/indexes/swap/all.hpp
    ${PROJECT_BINARY_DIR}/ql/instruments/all.hpp
    ${PROJECT_BINARY_DIR}/ql/instruments/bonds/all.hpp
    ${PROJECT_BINARY_DIR}/ql/legacy/all.hpp
    ${PROJECT_BINARY_DIR}/ql/legacy/libormarketmodels/all.hpp
    ${PROJECT_BINARY_DIR}/ql/math/all.hpp
    ${PROJECT_BINARY_DIR}/ql/math/copulas/all.hpp
    ${PROJECT_BINARY_DIR}/ql/math/distributions/all.hpp
    ${PROJECT_BINARY_DIR}/ql/math/integrals/all.hpp
    ${PROJECT_BINARY_DIR}/ql/math/interpolations/all.hpp
    ${PROJECT_BINARY_DIR}/ql/math/matrixutilities/all.hpp
    ${PROJECT_BINARY_DIR}/ql/math/ode/all.hpp
    ${PROJECT_BINARY_DIR}/ql/math/optimization/all.hpp
    ${PROJECT_BINARY_DIR}/ql/math/randomnumbers/all.hpp
    ${PROJECT_BINARY_DIR}/ql/math/solvers1d/all.hpp
    ${PROJECT_BINARY_DIR}/ql/math/statistics/all.hpp
    ${PROJECT_BINARY_DIR}/ql/methods/all.hpp
    ${PROJECT_BINARY_DIR}/ql/methods/finitedifferences/all.hpp
    ${PROJECT_BINARY_DIR}/ql/methods/finitedifferences/meshers/all.hpp
    ${PROJECT_BINARY_DIR}/ql/methods/finitedifferences/operators/all.hpp
    ${PROJECT_BINARY_DIR}/ql/methods/finitedifferences/schemes/all.hpp
    ${PROJECT_BINARY_DIR}/ql/methods/finitedifferences/solvers/all.hpp
    ${PROJECT_BINARY_DIR}/ql/methods/finitedifferences/stepconditions/all.hpp
    ${PROJECT_BINARY_DIR}/ql/methods/finitedifferences/utilities/all.hpp
    ${PROJECT_BINARY_DIR}/ql/methods/lattices/all.hpp
    ${PROJECT_BINARY_DIR}/ql/methods/montecarlo/all.hpp
    ${PROJECT_BINARY_DIR}/ql/models/all.hpp
    ${PROJECT_BINARY_DIR}/ql/models/equity/all.hpp
    ${PROJECT_BINARY_DIR}/ql/models/marketmodels/all.hpp
    ${PROJECT_BINARY_DIR}/ql/models/marketmodels/browniangenerators/all.hpp
    ${PROJECT_BINARY_DIR}/ql/models/marketmodels/callability/all.hpp
    ${PROJECT_BINARY_DIR}/ql/models/marketmodels/correlations/all.hpp
    ${PROJECT_BINARY_DIR}/ql/models/marketmodels/curvestates/all.hpp
    ${PROJECT_BINARY_DIR}/ql/models/marketmodels/driftcomputation/all.hpp
    ${PROJECT_BINARY_DIR}/ql/models/marketmodels/evolvers/all.hpp
    ${PROJECT_BINARY_DIR}/ql/models/marketmodels/evolvers/volprocesses/all.hpp
    ${PROJECT_BINARY_DIR}/ql/models/marketmodels/models/all.hpp
    ${PROJECT_BINARY_DIR}/ql/models/marketmodels/pathwisegreeks/all.hpp
    ${PROJECT_BINARY_DIR}/ql/models/marketmodels/products/all.hpp
    ${PROJECT_BINARY_DIR}/ql/models/marketmodels/products/multistep/all.hpp
    ${PROJECT_BINARY_DIR}/ql/models/marketmodels/products/onestep/all.hpp
    ${PROJECT_BINARY_DIR}/ql/models/marketmodels/products/pathwise/all.hpp
    ${PROJECT_BINARY_DIR}/ql/models/shortrate/all.hpp
    ${PROJECT_BINARY_DIR}/ql/models/shortrate/calibrationhelpers/all.hpp
    ${PROJECT_BINARY_DIR}/ql/models/shortrate/onefactormodels/all.hpp
    ${PROJECT_BINARY_DIR}/ql/models/shortrate/twofactormodels/all.hpp
    ${PROJECT_BINARY_DIR}/ql/models/volatility/all.hpp
    ${PROJECT_BINARY_DIR}/ql/patterns/all.hpp
    ${PROJECT_BINARY_DIR}/ql/pricingengines/all.hpp
    ${PROJECT_BINARY_DIR}/ql/pricingengines/asian/all.hpp
    ${PROJECT_BINARY_DIR}/ql/pricingengines/barrier/all.hpp
    ${PROJECT_BINARY_DIR}/ql/pricingengines/basket/all.hpp
    ${PROJECT_BINARY_DIR}/ql/pricingengines/bond/all.hpp
    ${PROJECT_BINARY_DIR}/ql/pricingengines/capfloor/all.hpp
    ${PROJECT_BINARY_DIR}/ql/pricingengines/cliquet/all.hpp
    ${PROJECT_BINARY_DIR}/ql/pricingengines/credit/all.hpp
    ${PROJECT_BINARY_DIR}/ql/pricingengines/exotic/all.hpp
    ${PROJECT_BINARY_DIR}/ql/pricingengines/forward/all.hpp
    ${PROJECT_BINARY_DIR}/ql/pricingengines/inflation/all.hpp
    ${PROJECT_BINARY_DIR}/ql/pricingengines/lookback/all.hpp
    ${PROJECT_BINARY_DIR}/ql/pricingengines/quanto/all.hpp
    ${PROJECT_BINARY_DIR}/ql/pricingengines/swap/all.hpp
    ${PROJECT_BINARY_DIR}/ql/pricingengines/swaption/all.hpp
    ${PROJECT_BINARY_DIR}/ql/pricingengines/vanilla/all.hpp
    ${PROJECT_BINARY_DIR}/ql/processes/all.hpp
    ${PROJECT_BINARY_DIR}/ql/quotes/all.hpp
    ${PROJECT_BINARY_DIR}/ql/termstructures/all.hpp
    ${PROJECT_BINARY_DIR}/ql/termstructures/credit/all.hpp
    ${PROJECT_BINARY_DIR}/ql/termstructures/inflation/all.hpp
    ${PROJECT_BINARY_DIR}/ql/termstructures/volatility/all.hpp
    ${PROJECT_BINARY_DIR}/ql/termstructures/volatility/capfloor/all.hpp
    ${PROJECT_BINARY_DIR}/ql/termstructures/volatility/equityfx/all.hpp
    ${PROJECT_BINARY_DIR}/ql/termstructures/volatility/inflation/all.hpp
    ${PROJECT_BINARY_DIR}/ql/termstructures/volatility/optionlet/all.hpp
    ${PROJECT_BINARY_DIR}/ql/termstructures/volatility/swaption/all.hpp
    ${PROJECT_BINARY_DIR}/ql/termstructures/yield/all.hpp
    ${PROJECT_BINARY_DIR}/ql/time/all.hpp
    ${PROJECT_BINARY_DIR}/ql/time/calendars/all.hpp
    ${PROJECT_BINARY_DIR}/ql/time/daycounters/all.hpp
    ${PROJECT_BINARY_DIR}/ql/utilities/all.hpp)

add_custom_command(OUTPUT ${QL_GENERATED_HEADERS}
    COMMAND ${CMAKE_COMMAND}
        -DSOURCE_DIR=${PROJECT_SOURCE_DIR}
        -DBINARY_DIR=${PROJECT_BINARY_DIR}
        -P ${PROJECT_SOURCE_DIR}/cmake/GenerateHeaders.cmake
    COMMENT "Generating headers..."
    WORKING_DIRECTORY ${PROJECT_BINARY_DIR})

add_library(ql_library
    ${QL_SOURCES}
    ${QL_HEADERS}
    ${QL_CONFIGURED_HEADERS}
    ${QL_GENERATED_HEADERS})

set_target_properties(ql_library PROPERTIES
    EXPORT_NAME ${PACKAGE_NAME}
    OUTPUT_NAME ${PACKAGE_NAME}
    VERSION ${QUANTLIB_VERSION}
    SOVERSION ${QUANTLIB_VERSION_MAJOR})

target_compile_definitions(ql_library PRIVATE
    QL_COMPILATION)

target_compile_options(ql_library PRIVATE
    ${OpenMP_CXX_FLAGS})

if(MSVC AND CMAKE_UNITY_BUILD)
    # for Unity builds, we need to add /bigobj
    target_compile_options(ql_library PRIVATE "/bigobj")
endif()

if(NOT "${QL_EXTRA_LINK_LIBRARIES}" STREQUAL "")
    target_link_libraries(ql_library PUBLIC ${QL_EXTRA_LINK_LIBRARIES})
endif()

target_include_directories(ql_library PUBLIC
    $<BUILD_INTERFACE:${PROJECT_BINARY_DIR}>
    $<BUILD_INTERFACE:${PROJECT_SOURCE_DIR}>
    $<INSTALL_INTERFACE:${QL_INSTALL_INCLUDEDIR}>)

target_include_directories(ql_library SYSTEM PUBLIC
    ${Boost_INCLUDE_DIRS}
    ${OpenMP_CXX_INCLUDE_DIRS})

target_link_libraries(ql_library PUBLIC
    ${OpenMP_CXX_LIBRARIES})

install(TARGETS ql_library EXPORT QuantLibTargets
    ARCHIVE DESTINATION ${QL_INSTALL_LIBDIR}
    LIBRARY DESTINATION ${QL_INSTALL_LIBDIR})

# Install ql source headers preserving ql hierarchy
foreach(file ${QL_HEADERS})
    get_filename_component(dir ${file} DIRECTORY)
    install(FILES ${file} DESTINATION "${QL_INSTALL_INCLUDEDIR}/ql/${dir}")
endforeach()

# Install configured headers from the build directory
foreach(file ${QL_CONFIGURED_HEADERS})
    install(FILES ${file} DESTINATION "${QL_INSTALL_INCLUDEDIR}/ql/")
endforeach()

# Install generated headers from the build directory
foreach(file ${QL_GENERATED_HEADERS})
    get_filename_component(dir ${file} DIRECTORY)
    file(RELATIVE_PATH path ${PROJECT_BINARY_DIR} ${dir})
    install(FILES ${file} DESTINATION "${QL_INSTALL_INCLUDEDIR}/${path}")
endforeach()

# Install config scripts for people using `find_package(QuantLib::QuantLib CONFIG ...)`
include(CMakePackageConfigHelpers)
write_basic_package_version_file(
    "${PROJECT_BINARY_DIR}/cmake/QuantLibConfigVersion.cmake"
    VERSION ${QL_VERSION}
    COMPATIBILITY AnyNewerVersion
)
export(EXPORT QuantLibTargets
    FILE "${PROJECT_BINARY_DIR}/cmake/QuantLibTargets.cmake"
    NAMESPACE QuantLib::
)
configure_file("${PROJECT_SOURCE_DIR}/cmake/QuantLibConfig.cmake.in"
    "${PROJECT_BINARY_DIR}/cmake/QuantLibConfig.cmake"
    COPYONLY
)
configure_package_config_file("${PROJECT_SOURCE_DIR}/cmake/QuantLibConfig.cmake.in"
    "${PROJECT_BINARY_DIR}/cmake/QuantLibConfig.cmake"
    INSTALL_DESTINATION "${QL_INSTALL_CMAKEDIR}"
)
install(EXPORT QuantLibTargets
    FILE QuantLibTargets.cmake
    NAMESPACE QuantLib::
    DESTINATION "${QL_INSTALL_CMAKEDIR}"
)
install(FILES "${PROJECT_BINARY_DIR}/cmake/QuantLibConfig.cmake"
    "${PROJECT_BINARY_DIR}/cmake/QuantLibConfigVersion.cmake"
    DESTINATION "${QL_INSTALL_CMAKEDIR}"
)
