cmake_minimum_required(VERSION 3.29)

project(graphics-engine)

#exports compile_commands.json
set(CMAKE_EXPORT_COMPILE_COMMANDS ON CACHE INTERNAL "")

# Prevent GLFW from building examples and tests
set(GLFW_BUILD_EXAMPLES OFF CACHE BOOL "" FORCE)
set(GLFW_BUILD_TESTS OFF CACHE BOOL "" FORCE)

# Add GLFW as a subproject
add_subdirectory(vendor/glfw)
add_subdirectory(vendor/glad)

set(SOURCES
    src/main.cpp
)

add_executable(graphics-engine ${SOURCES})

# Link against GLFW
target_link_libraries(graphics-engine glfw glad)

target_include_directories(graphics-engine
    PRIVATE
    ${PROJECT_SOURCE_DIR}/include
    ${PROJECT_SOURCE_DIR}/vendor
)
