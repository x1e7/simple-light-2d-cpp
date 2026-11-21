cmake_minimum_required(VERSION 3.24)
project(simple-light-2d-cpp LANGUAGES CXX)

set(CMAKE_CXX_STANDARD 20)
set(CMAKE_CXX_STANDARD_REQUIRED ON)
set(CMAKE_CXX_EXTENSIONS OFF)

if(CMAKE_CXX_COMPILER_ID STREQUAL "Clang")
    add_compile_options(-O3 -march=native -ffast-math -Wall -Wextra)
endif()

add_executable(simple-light-2d-cpp
    src/main.cpp
)

target_link_options(simple-light-2d-cpp PRIVATE
    -Wl,-subsystem,console
    -Xlinker --entry=mainCRTStartup
)
target_link_libraries(simple-light-2d-cpp PRIVATE m)
