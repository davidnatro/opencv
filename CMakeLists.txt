cmake_minimum_required(VERSION 3.27)
project(opencv)

set(CMAKE_CXX_STANDARD 17)

add_subdirectory(${PROJECT_SOURCE_DIR}/third_party/opencv)

add_executable(opencv main.cpp)

target_link_libraries(opencv PUBLIC opencv_core)
target_include_directories(opencv PUBLIC ${PROJECT_BINARY_DIR} ${PROJECT_SOURCE_DIR}/third_party/opencv/modules/core/include)
