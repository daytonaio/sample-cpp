cmake_minimum_required(VERSION 3.0.0)
project(HelloWorld VERSION 0.1.0 LANGUAGES C CXX)

include(CTest)
enable_testing()

add_executable(HelloWorld main.cpp)

configure_file(hello.h.in hello.h)

target_include_directories(HelloWorld PUBLIC
                           "${PROJECT_BINARY_DIR}"
                           )

set(CPACK_PROJECT_NAME ${PROJECT_NAME})
set(CPACK_PROJECT_VERSION ${PROJECT_VERSION})
include(CPack)

install (TARGETS HelloWorld DESTINATION bin)