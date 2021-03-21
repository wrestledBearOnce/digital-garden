---
title: vcpkg
---

**With Windows and Visual Studio 2019**

## Install

```bash
> git clone https://github.com/microsoft/vcpkg
> .\vcpkg\bootstrap-vcpkg.bat
> .\vcpkg integrate install
(ADMIN) > .\vcpkg integrate install
```

## Use

```bash
.\vpckg install package:x64-windows
.\vcpkg search package:x64-windows
```

### References

[Vcpkg GitHub repo](https://github.com/microsoft/vcpkg)

## Manifest example with specific version

```json
{
    "name": "versions-test",
    "version": "1.0.0",
    "dependencies": [
        {
            "name": "fmt",
            "version>=": "7.1.3"
        },
        "zlib"
    ],
    "builtin-baseline": "b60f003ccf5fe8613d029f49f835c8929a66eb61"
}
```

Activate in [[CMake]]

```cmake
cmake_minimum_required(VERSION 3.18)

set(VCPKG_FEATURE_FLAGS "versions")
project(versions-test CXX)

add_executable(main main.cpp)

find_package(ZLIB REQUIRED)
find_package(fmt CONFIG REQUIRED)
target_link_libraries(main PRIVATE ZLIB::ZLIB fmt::fmt)
```

### References

- [Article](https://devblogs.microsoft.com/cppblog/take-control-of-your-vcpkg-dependencies-with-versioning-support/)

- [Version scheme](https://github.com/microsoft/vcpkg/blob/master/docs/users/versioning.reference.md#version-schemes)

## Remove installation after integrate install / change integration to point to new folder

Change *.txt file in `C:\Users\$(Username)\AppData\Local\vcpkg\vcpkg.path.txt`