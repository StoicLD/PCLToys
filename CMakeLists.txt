cmake_minimum_required(VERSION 3.12)
project(PCLTest1)

set(CMAKE_CXX_STANDARD 14)
include_directories(SYSTEM "/Applications/Xcode.app/Contents/Developer/Toolchains/XcodeDefault.xctoolchain/usr/include/c++/v1")
find_package(PCL 1.3 REQUIRED COMPONENTS common io)
include_directories(${PCL_INCLUDE_DIRS})

#set(CMAKE_EXE_LINKER_FLAGS "${CMAKE_EXE_LINKER_FLAGS} -stdlib=libc++ -lc++abi")
link_directories(${PCL_LIBRARY_DIRS})

add_definitions(${PCL_DEFINITIONS})
add_executable(PCLTest1 main.cpp)
target_link_libraries (PCLTest1 ${PCL_LIBRARIES})
