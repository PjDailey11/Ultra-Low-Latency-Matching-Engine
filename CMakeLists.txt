cmake_minimum_required(VERSION 3.10)

# Define the project and the language (C++)
project(MatchingEngine CXX)

set(CMAKE_CXX_STANDARD 23)
set(CMAKE_CXX_STANDARD_REQUIRED True)

# Set global compiler flags for strict warnings, max optimization, debug symbols, and ASan
set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -Wall -Wextra -Werror -O3 -g -fsanitize=address")

# Ensure the linker also knows to build with AddressSanitizer
set(CMAKE_EXE_LINKER_FLAGS "${CMAKE_EXE_LINKER_FLAGS} -fsanitize=address")

# Tell CMake to build an executable named 'engine' from 'engine.c'
add_executable(engine
    main.cpp
)
target_link_libraries(engine uring)

