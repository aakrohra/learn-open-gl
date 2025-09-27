cmake_minimum_required(VERSION 3.10)
project(learn_open_gl)

find_package(glfw3 3.4 REQUIRED CONFIG)

find_package(OpenGL REQUIRED)

add_executable(main src/main.cpp src/glad.c src/shader.cpp)

file(COPY ${CMAKE_SOURCE_DIR}/src/shaders DESTINATION ${CMAKE_BINARY_DIR})

target_include_directories(main
    PUBLIC
    ${CMAKE_SOURCE_DIR}/include
)

target_link_libraries(main
    PUBLIC
    glfw
)

target_link_libraries(main PRIVATE "-framework OpenGL" "-framework GLUT")

