set(QL_SOURCES
    instruments/vanillaswap.cpp
)

set(QL_HEADERS
    instruments/vanillaswap.hpp
)

set(QL_CONFIGURED_HEADERS
    ${PROJECT_BINARY_DIR}/ql/config.hpp
    ${PROJECT_BINARY_DIR}/ql/qldefines.hpp)


set(QL_GENERATED_HEADERS "")


add_library(ql_library ${QL_SOURCES} ${QL_HEADERS})

set_target_properties(ql_library PROPERTIES
        EXPORT_NAME ${PACKAGE_NAME}
        OUTPUT_NAME ${PACKAGE_NAME}
        VERSION ${QUANTLIB_VERSION}
        SOVERSION ${QUANTLIB_VERSION_MAJOR})


target_include_directories(ql_library PUBLIC
        $<BUILD_INTERFACE:${PROJECT_BINARY_DIR}>
        $<BUILD_INTERFACE:${PROJECT_SOURCE_DIR}>
        $<INSTALL_INTERFACE:${QL_INSTALL_INCLUDEDIR}>)