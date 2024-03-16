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

target_include_directories(ql_library PUBLIC "")