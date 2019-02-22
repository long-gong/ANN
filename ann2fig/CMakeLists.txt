set(target ann2fig)
set(src "ann2fig.cpp")

add_executable(${target} ${src})
target_link_libraries(${target} ANN)
install(TARGETS ${target}
        DESTINATION ${PROJECT_BINARY_DIR})