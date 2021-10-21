cmake_minimum_required(VERSION 3.0 FATAL_ERROR)
project(test)

find_package(ROOT)

set(CMAKE_CXX_STANDARD 17)

ROOT_GENERATE_DICTIONARY(G__test test.h LINKDEF LinkDef.h)

add_library(test SHARED test.h  G__test.cxx)
target_link_libraries(test ${ROOT_LIBRARIES})
target_include_directories(test PUBLIC ${CMAKE_CURRENT_LIST_DIR})


