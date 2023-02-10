cmake_minimum_required(VERSION 3.2)

project(Sandbox)

set(SOURCE_FILES
    vendor/glad/src/glad.c
    src/main.cpp)

add_executable(Sandbox ${SOURCE_FILES})

# GLAD as part of sources

target_include_directories(Sandbox PUBLIC ${CMAKE_CURRENT_SOURCE_DIR}/vendor/glad/include)

# GLFW as a subproject

option(GLFW_BUILD_DOCS OFF)
option(GLFW_BUILD_TESTS OFF)
option(GLFW_BUILD_EXAMPLES OFF)

add_subdirectory(${CMAKE_CURRENT_SOURCE_DIR}/vendor/glfw)

target_link_libraries(Sandbox glfw)