cmake_minimum_required(VERSION 3.0.0)
project(cpp_doxygen_sphinx VERSION 0.1.0 LANGUAGES C CXX)

include(CTest)
enable_testing()

add_library(cpp_doxygen_sphinx cpp_doxygen_sphinx.cpp)

set(CPACK_PROJECT_NAME ${PROJECT_NAME})
set(CPACK_PROJECT_VERSION ${PROJECT_VERSION})
include(CPack)
