cmake_minimum_required(VERSION 3.5.1)

project(math CXX)

add_definitions(-std=c++1z -Wall)
include_directories(/usr/local/include)

set(HEADERS access.hpp analysis.hpp bezier.hpp constants.hpp ease.hpp interleave.hpp interpolation.hpp linear.hpp normalize.hpp random.hpp sigmoid.hpp sinusoid.hpp spline.hpp statistics.hpp utility.hpp)

set(SOURCES bezier.cpp)

add_library(math STATIC ${HEADERS} ${SOURCES})
install(TARGETS math DESTINATION lib)

target_sources(math PRIVATE ${HEADERS} ${SOURCES})
source_group(\\ FILES ${HEADERS} ${SOURCES})
install (FILES ${HEADERS} DESTINATION include/dsperados/math)
