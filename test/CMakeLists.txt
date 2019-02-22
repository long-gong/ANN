set(SRCs "rand.cpp" "ann_test.cpp")
set(HEADERs "rand.h")

set(target "ann_test")
add_executable(${target} ${SRCs} ${HEADERs})
target_link_libraries(${target}
        ANN)
add_test(NAME ${PROJECT_NAME}_test
        COMMAND $<TARGET_FILE:${target}>)

# Copy test files
set(test_data_files
        "${CMAKE_CURRENT_SOURCE_DIR}/test1.in"
        "${CMAKE_CURRENT_SOURCE_DIR}/test1.save"
        "${CMAKE_CURRENT_SOURCE_DIR}/test1-data.pts"
        "${CMAKE_CURRENT_SOURCE_DIR}/test1-query.pts"
        "${CMAKE_CURRENT_SOURCE_DIR}/test2.in"
        "${CMAKE_CURRENT_SOURCE_DIR}/test2.save"
        "${CMAKE_CURRENT_SOURCE_DIR}/test2-data.pts"
        "${CMAKE_CURRENT_SOURCE_DIR}/test2-query.pts")
file(
        COPY ${test_data_files}
        DESTINATION ${PROJECT_BINARY_DIR}
)

# Install binary
install(
        TARGETS ${target}
        DESTINATION ${PROJECT_BINARY_DIR}
)