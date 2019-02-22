set(target "ann_sample")
set(src "ann_sample.cpp")

add_executable(${target}
        ${src})
target_link_libraries(${target}
        ANN)

set(sample_data_files
        "${CMAKE_CURRENT_SOURCE_DIR}/data.pts"
        "${CMAKE_CURRENT_SOURCE_DIR}/query.pts"
        "${CMAKE_CURRENT_SOURCE_DIR}/sample.save")
file(COPY ${sample_data_files}
        DESTINATION ${PROJECT_BINARY_DIR})

install(TARGETS ${target}
        DESTINATION ${PROJECT_BINARY_DIR})