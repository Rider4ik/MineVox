cmake_minimum_required(VERSION 3.20)

project(MineVox)

set(CMAKE_CXX_STANDARD 20 CACHE STRING "C++ standard to use")
set_property(CACHE CMAKE_CXX_STANDARD PROPERTY STRINGS 14 17 20 23)

file(GLOB SOURCES_CXX "src/*.cpp" "src/*/*.cpp" "src/*/*/*.cpp" "src/*/*/*/*.cpp")


find_package(OpenGL REQUIRED)

add_subdirectory("${CMAKE_SOURCE_DIR}/libs/glfw")
add_subdirectory("${CMAKE_SOURCE_DIR}/libs/glm")


add_library(glew STATIC
    "${CMAKE_SOURCE_DIR}/libs/glew/src/glew.c"
)

target_include_directories(glew PUBLIC  
    "${CMAKE_SOURCE_DIR}/libs/glew/include"
)

target_compile_definitions(glew PUBLIC GLEW_STATIC)

target_link_libraries(glew PUBLIC OpenGL::GL)

add_executable(${PROJECT_NAME}
    ${SOURCES_CXX}
)

target_include_directories(${PROJECT_NAME}
    PRIVATE
        ${CMAKE_HOME_DIRECTORY}/libs/srs
        ${CMAKE_HOME_DIRECTORY}/libs/glfw/include/
        ${CMAKE_HOME_DIRECTORY}/libs/glm
        
)

target_link_libraries(${PROJECT_NAME}
    PRIVATE
        glfw
        OpenGL::GL
        glew
        glm::glm
)









