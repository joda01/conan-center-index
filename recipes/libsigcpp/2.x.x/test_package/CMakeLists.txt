cmake_minimum_required(VERSION 3.15)
project(test_package LANGUAGES CXX)

find_package(PkgConfig REQUIRED)
pkg_search_module(SIGCPP IMPORTED_TARGET REQUIRED sigc++-2.0)

add_executable(${PROJECT_NAME} test_package.cpp)
target_link_libraries(${PROJECT_NAME} PRIVATE PkgConfig::SIGCPP)
target_compile_features(${PROJECT_NAME} PRIVATE cxx_std_11)
