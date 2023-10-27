cmake_minimum_required(VERSION 3.10)
project(Rasterizer)
set(OpenCV_DIR D:/dependency/opencv/build/x64/vc16/lib)
find_package(OpenCV REQUIRED)

set(CMAKE_CXX_STANDARD 17)

add_executable(Rasterizer main.cpp rasterizer.hpp rasterizer.cpp global.hpp Triangle.hpp Triangle.cpp)
target_link_libraries(Rasterizer PUBLIC  ${OpenCV_LIBRARIES})
target_include_directories(Rasterizer PRIVATE D:/dependency/eigen3.3.9)
