#Cmake 最低版本号
cmake_minimum_required(VERSION 3.10)
#Cmake 指定C++ 标准
set(CMAKE_CXX_STANDARD 17)
# 设置项目输出文件目录
set(OUTPUT_DIR ${PROJECT_BINARY_DIR}/bin)
set(CMAKE_RUNTIME_OUTPUT_DIRECTORY ${OUTPUT_DIR})	
set(CMAKE_ARCHIVE_OUTPUT_DIRECTORY ${OUTPUT_DIR})	
set(CMAKE_LIBRARY_OUTPUT_DIRECTORY ${OUTPUT_DIR})	
set(CMAKE_RUNTIME_OUTPUT_DIRECTORY_DEBUG ${OUTPUT_DIR})	
set(CMAKE_ARCHIVE_OUTPUT_DIRECTORY_DEBUG ${OUTPUT_DIR})	
set(CMAKE_LIBRARY_OUTPUT_DIRECTORY_DEBUG ${OUTPUT_DIR})	
set(CMAKE_RUNTIME_OUTPUT_DIRECTORY_DEBUG ${OUTPUT_DIR})	
set(CMAKE_ARCHIVE_OUTPUT_DIRECTORY_RELEASE ${OUTPUT_DIR})	
set(CMAKE_LIBRARY_OUTPUT_DIRECTORY_RELEASE ${OUTPUT_DIR})	


#项目名
project(demo)
# 添加依赖库
set(OpenCV_DIR  "D:/dependency/opencv/build/x64/vc16/lib")
find_package(OpenCV REQUIRED) 

# 添加依赖库 way2
set(CMAKE_MODULE_PATH "${CMAKE_CURRENT_LIST_DIR}/cmake;${CMAKE_MODULE_PATH}") 
find_package(OpenCV/REQUIRED)

#所需代码
file(GLOB_RECURSE srcs CONFIGURE_DEPENDS src/*.cpp include/*.h)

add_executable(demo ${srcs})
#链接头文件路径
target_include_directories(demo PUBLIC include)
#链接依赖库的LIB
target_link_libraries(demo PUBLIC ${OpenCV_LIBS})
message("link opencvlib :"${OpenCV_LIBS})


