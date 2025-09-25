cmake_minimum_required(VERSION 3.10)
project(learn_open_gl)

find_package(glfw3 3.4 REQUIRED CONFIG)

find_package(OpenGL REQUIRED)

add_executable(main src/main.cpp src/glad.c)

target_include_directories(main
    PRIVATE
    ${CMAKE_SOURCE_DIR}/include
)

target_link_libraries(main
    PRIVATE
    glfw
)

target_link_libraries(main PRIVATE "-framework OpenGL" "-framework GLUT")

