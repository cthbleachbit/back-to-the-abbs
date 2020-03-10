cmake_minimum_required (VERSION 3.0)
project (CONFIG4CPP)
set (CONFIG4CPP_VERSION_MAJOR 1)
set (CONFIG4CPP_VERSION_MINOR 1)

set(CMAKE_CXX_STANDARD 98)

include_directories(include)

# Source files
add_subdirectory(src)
