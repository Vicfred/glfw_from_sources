# https://www.glfw.org/docs/latest/build_guide.html#build_link_cmake_source
cmake_minimum_required(VERSION 3.13.4)

project(tamachan)

set(CMAKE_CXX_STANDARD 17)
set(CMAKE_EXPORT_COMPILE_COMMANDS ON)

find_package(OpenGL REQUIRED)

set(GLFW_BUILD_DOCS OFF CACHE BOOL "" FORCE)
set(GLFW_BUILD_TESTS OFF CACHE BOOL "" FORCE)
set(GLFW_BUILD_EXAMPLES OFF CACHE BOOL "" FORCE)

add_subdirectory(external/glfw)

add_executable(tamachan tamachan.cpp)
target_link_libraries(tamachan glfw OpenGL::GL)
