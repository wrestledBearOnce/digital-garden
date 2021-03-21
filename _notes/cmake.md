---
title: CMake
---

CMake is a build system for [[cpp]] and [[CSharp]]

## Minimal example

```cmake
cmake_minimum_required(VERSION 3.18)

project(${PROJECT_NAME} CXX)

add_executable(main main.cpp)

find_package(ZLIB REQUIRED)
find_package(fmt CONFIG REQUIRED)

target_link_libraries( main 
    PRIVATE 
        ZLIB::ZLIB 
        fmt::fmt
)
```

ref: https://cliutils.gitlab.io/modern-cmake/