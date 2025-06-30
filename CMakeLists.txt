cmake_minimum_required(VERSION 3.21)
project(conan_boost_example)

set(CMAKE_CXX_STANDARD 17)

find_package(Boost REQUIRED)

add_executable(main main.cpp)
target_link_libraries(main PRIVATE Boost::boost)

