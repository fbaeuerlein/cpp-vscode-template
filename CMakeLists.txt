cmake_minimum_required(VERSION 3.16.0)
enable_testing()


project(vscode-template)
add_executable(main main.cpp)

add_subdirectory(test)
