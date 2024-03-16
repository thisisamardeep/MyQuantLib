add_executable(CVAIRS CVAIRS.cpp)
message(44444444444444)
message(44 ${QL_THREAD_LIBRARIES})
target_link_libraries(CVAIRS ql_library ${QL_THREAD_LIBRARIES})
