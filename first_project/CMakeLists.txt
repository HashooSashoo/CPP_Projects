cmake_minimum_required(VERSION 3.20)
project(MyProject)

set(CMAKE_CXX_STANDARD 20)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

add_executable(MyProject src/main.cpp)

target_compile_options(MyProject PRIVATE 
    -Wall               # commonly useful warnings (though not all of them, this is a historical name lol)
    -Wextra             # additional warnings
    -Wshadow            # warning on variable shadowing (basically when you rename a var with lower scope the same as one in higher scope)
    -Wconversion        # warning on implicit type conversions that could lose data (int to char, double to int, etc.)
    -Wsign-conversion   # warning on losing sign on numbers
    -pedantic-errors    # makes it so that all code you write must be ISO C++, so it can compile with any compiler, not just clang
    -Werror             # all warnings are treated as errors (might get annoying but I NEED the discipline lol)
)
