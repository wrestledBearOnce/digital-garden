---
title: Eigen3
---

Eigen3 is a math library for [[cpp]].

## Installation with [[vcpkg]]

```bash
.\vcpkg.exe install eigen3:x64-windows
```

## Use with [[CMake]]

```cmake
find_package(Eigen3 CONFIG REQUIRED)
target_link_libraries( main 
    PRIVATE 
        Eigen3::Eigen
)
```

## Tipps & Tricks

Use this header include for cross compilation purposes.
Should work for all platforms.

```cpp
#include <eigen3/Eigen/Dense>
```
