cmake_minimum_required(VERSION 3.5)

project(test)
add_executable(test test.cpp)
target_include_directories(test PRIVATE include)

set(CMAKE_EXPORT_COMPILE_COMMANDS ON)
if(EMSCRIPTEN)
    set_target_properties(${PROJECT_NAME} PROPERTIES SUFFIX ".html")
    set(LFLAGS "-s USE_GLFW=3 -s MIN_WEBGL_VERSION=2 -s MAX_WEBGL_VERSION=2")
    set_target_properties(${PROJECT_NAME} PROPERTIES LINK_FLAGS "${LFLAGS}")
    set_target_properties(${PROJECT_NAME} PROPERTIES COMPILE_FLAGS "-O2")
endif()