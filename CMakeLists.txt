set(CMAKE_CXX_STANDARD 11)
cmake_minimum_required(VERSION 2.8)
project(tcp)
set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -std=c++11")
file(GLOB SRC ${CMAKE_CURRENT_SOURCE_DIR}/tcpserver_main.cpp tcpserver.cpp response.cpp)
file(GLOB SRC1 ${CMAKE_CURRENT_SOURCE_DIR}/tcpclient_main.cpp response.cpp)
#get_filename_component(PARENT_DIR "${CMAKE_CURRENT_SOURCE_DIR}/.." ABSOLUTE)
include_directories(${CMAKE_CURRENT_SOURCE_DIR})
#link_directories(${PARENT_DIR}/xsocket/)
set(EXECUTABLE_OUTPUT_PATH ../build)
add_executable(tcpserver ${SRC})
add_executable(tcpclient ${SRC1})
target_link_libraries(tcpserver pthread)
#target_link_libraries(tcpserver XTcp)