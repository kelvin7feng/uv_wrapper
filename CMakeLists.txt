#项目名称，使用语言
PROJECT(LIBUV_WRAPPER C CXX)
#CMake最低版本
CMAKE_MINIMUM_REQUIRED(VERSION 2.8)
SET(CMAKE_CXX_STANDARD 11)
SET(CMAKE_CXX_STANDARD_REQUIRED ON)
INCLUDE(CheckCXXCompilerFlag)  
CHECK_CXX_COMPILER_FLAG("-std=c++11" COMPILER_SUPPORTS_CXX11)  
if(COMPILER_SUPPORTS_CXX11)  
	SET(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -std=c++11")  
else()  
	MESSAGE(STATUS "The compiler ${CMAKE_CXX_COMPILER} has no C++11 support. Please use a different C++ compiler.")  
endif() 
#设置源文
SET(SRC_LIST main.cpp)
#设置变量
SET(PROJECT_ROOT_PATH "${CMAKE_CURRENT_SOURCE_DIR}")
#设置头文件搜索目录
INCLUDE_DIRECTORIES("${PROJECT_ROOT_PATH}/third_party/libuv-v1.9.1/include/")
#增加库文件搜索
LINK_DIRECTORIES("${PROJECT_ROOT_PATH}/third_party/libuv-v1.9.1/.libs/")
#执行编译
ADD_EXECUTABLE(main ${SRC_LIST})
#链接第三方库, uv库需要安装libuv,参考evernote笔记
TARGET_LINK_LIBRARIES(main uv)
