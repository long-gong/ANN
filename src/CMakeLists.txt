file(GLOB SRCs "*.cpp")
file(GLOB HEADERs "*.h")


set(target ANN)
add_library(${target} STATIC
        "${SRCs}"
        "${HEADERs}")
# Install binary
install(
        TARGETS ${target}
        DESTINATION ${PROJECT_LIB_DIR}
)
