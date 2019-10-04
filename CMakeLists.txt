cmake_minimum_required(VERSION 3.12)
project(simplyfile)

include_directories(include/simplyfile)
include_directories(include/simplyfile/socket)

file(GLOB_RECURSE SOURCES *.cpp)


if (CMAKE_VERSION VERSION_LESS 3.15)
    add_library(${PROJECT_NAME} OBJECT ${SOURCES})
else()
    add_library(${PROJECT_NAME} ${SOURCES})
endif()
target_include_directories(${PROJECT_NAME} PUBLIC include)

target_link_libraries(${PROJECT_NAME} PUBLIC)
set_property(TARGET ${PROJECT_NAME} PROPERTY CXX_STANDARD 17)