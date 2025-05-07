cmake_minimum_required(VERSION 3.29)

project(graphics-engine)

set(CMAKE_EXPORT_COMPILE_COMMANDS ON CACHE INTERNAL "")
set(SOURCES
    src/main.cpp
)

add_executable(graphics-engine ${SOURCES})

target_include_directories(graphics-engine
    PRIVATE
    ${PROJECT_SOURCE_DIR}/include
)
