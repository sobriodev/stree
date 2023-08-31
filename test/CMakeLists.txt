cmake_minimum_required(VERSION 3.16)
project(stree_test)
include_directories(${stree_SOURCE_DIR}/include)

set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -Wall -Wextra -Wpedantic -Werror")

include(FetchContent)
FetchContent_Declare(
        googletest
        URL https://github.com/google/googletest/archive/refs/tags/v1.14.0.zip
)
FetchContent_MakeAvailable(googletest)

add_executable(test1 test1.cpp)
target_link_libraries(test1 gtest_main)
add_test(NAME test1 COMMAND test1)