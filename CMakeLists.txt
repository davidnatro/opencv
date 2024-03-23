cmake_minimum_required(VERSION 3.27)
project(opencv)

set(CMAKE_CXX_STANDARD 17)

add_subdirectory(${PROJECT_SOURCE_DIR}/third_party/opencv)
add_subdirectory(${PROJECT_SOURCE_DIR}/third_party/boost)

add_executable(opencv main.cpp)

target_link_libraries(opencv PUBLIC opencv_core Boost::algorithm)
target_include_directories(opencv PUBLIC
        ${PROJECT_BINARY_DIR}
        ${PROJECT_SOURCE_DIR}/third_party/opencv/modules/core/include
        ${PROJECT_SOURCE_DIR}/third_party/boost/libs/algorithm/include
)
