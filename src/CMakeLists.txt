cmake_minimum_required(VERSION 3.10)
project(CubeGL)

set(CMAKE_CXX_STANDARD 23)
set(CMAKE_CXX_STANDARD_REQUIRED True)
set(CMAKE_EXPORT_COMPILE_COMMANDS ON)

# include_directories("./glfw_win/include") # Windows
# link_directories("./glfw_win/lib-vc2022") # Windows

include_directories(lib)

add_executable(cube main.cc)
add_library(vertex vertex.cc)
add_library(shader shader.cc)
add_library(texture texture.cc)
add_library(vertexbuffer vertexbuffer.cc)
add_library(indexbuffer indexbuffer.cc)
add_library(vertexarray vertexarray.cc)

# target_link_libraries(cube shader glfw3) # Windows
target_link_libraries(cube shader vertex texture vertexbuffer indexbuffer vertexarray glfw)
