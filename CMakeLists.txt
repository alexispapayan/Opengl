#minimum version required
cmake_minimum_required(VERSION 2.8.14)

#add project
project(Opengl_tutorials)

#including subdirectories
add_subdirectory(${CMAKE_SOURCE_DIR}/libraries/glfw-3.2.1/)
add_subdirectory(${CMAKE_SOURCE_DIR}/libraries/glad-master)
add_subdirectory(${CMAKE_SOURCE_DIR}/projects)
