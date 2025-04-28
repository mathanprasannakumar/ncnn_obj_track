cmake_minimum_required(VERSION 3.30)
project(ncnn_obj_track)

SET(CMAKE_BUILD_TYPE "Debug")
find_package(ncnn REQUIRED)
find_package(OpenCV REQUIRED)
find_package(Eigen3 REQUIRED)

include_directories(include)
include_directories(${OpenCV_INCLUDE_DIRS} ${NCNN_INCLUDE_DIRS} ${EIGEN3_INCLUDE_DIR})

file(GLOB_RECURSE SRC_FILES src/*.cpp)

add_executable(ncnn_obj_track ${SRC_FILES})
target_link_libraries(ncnn_obj_track ncnn ${OpenCV_LIBS} ${EIGEN3_LIBRARIES})
