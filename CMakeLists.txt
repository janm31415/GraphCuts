cmake_minimum_required(VERSION 3.14)

project(GraphCut)

set(HDRS
block.h
energy.h
GCoptimization.h
graph.h
graph.hpp
LinkedBlockList.h
maxflow.hpp
)

set(SRCS
GCoptimization.cpp
LinkedBlockList.cpp
)

add_library(graph_cuts STATIC ${HDRS} ${SRCS})

add_executable(graph_cut_example example.cpp)

target_include_directories(graph_cuts PUBLIC ${graph_cuts_SOURCE_DIR})

target_link_libraries(graph_cut_example PRIVATE	graph_cuts)