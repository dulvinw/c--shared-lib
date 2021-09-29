cmake_minimum_required(VERSION 3.0.0)
project(static-link VERSION 0.1.0)

include(CTest)
enable_testing()

add_executable(static-link main.cpp)
target_link_libraries(static-link PUBLIC mylib)
include_directories(include)
target_link_directories(static-link PUBLIC /usr/local/lib)
target_include_directories(static-link PUBLIC /usr/local/include)

set(CPACK_PROJECT_NAME ${PROJECT_NAME})
set(CPACK_PROJECT_VERSION ${PROJECT_VERSION})
include(CPack)
