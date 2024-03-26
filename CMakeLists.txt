cmake_minimum_required(VERSION 3.0.0)

set(CMAKE_CXX_FLAGS_DEBUG "-O3 -Wall")

project(cpp_doxygen_sphinx VERSION 0.1.0)

include(CTest)
enable_testing()

# Source and header dir
set(PROJECT_SOURCE_DIR "src")
set(PROJECT_INCLUDE_DIR "include")

# Source files, without extensions or directory names
# Here assuming each file has both header and impl
set(SRC_FILES cpp_doxygen_sphinx)

# Create SOURCE_FILES
foreach(file ${SRC_FILES})
	list(APPEND SOURCE_FILES
        ${PROJECT_SOURCE_DIR}/${file}.cpp
        ${PROJECT_INCLUDE_DIR}/${file}.hpp
	)
endforeach()

# Set up such that your IDE organizes the files correctly
source_group(TREE ${CMAKE_CURRENT_SOURCE_DIR} FILES ${SOURCE_FILES})

add_library(cpp_doxygen_sphinx ${SOURCE_FILES})

set(CPACK_PROJECT_NAME ${PROJECT_NAME})
set(CPACK_PROJECT_VERSION ${PROJECT_VERSION})
include(CPack)