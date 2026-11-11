
# MineVox

A Minecraft clone written in C++ using OpenGL and CMake.


**STILL IN PROGRESS**

# How to build

## Requirements

MinevVox uses **CMake Presets** to configure and build the project with different C++ compilers and language standards.

Required tools:

- **CMake:** 3.24 or newer
- **Ninja:** Required for Clang, GCC and MinGW builds


## Supported Compilers

| Compiler | CMake Generator | Architecture |
|---|---|---|
| Clang | Ninja | x64 / platform-dependent |
| GCC | Ninja | x64 / platform-dependent |
| MSVC | Visual Studio 17 2022 | x64 |
| MinGW GCC | Ninja | x64 / platform-dependent |

## Supported C++ Standards

The project provides build configurations for the following C++ standards:

| C++ Standard | CMake Value |
|---|---|
| C++14 | `14` |
| C++17 | `17` |
| C++20 | `20` |
| C++23 | `23` |

Each supported compiler has separate configurations for all four language standards.

## Building the Project

All builds are performed using CMake Presets from the project root directory.

### Clang

Configure and build:

```bash
cmake --preset clang-14
cmake --build --preset clang-14
```

Available presets:

```bash
cmake --preset clang-14
cmake --preset clang-17
cmake --preset clang-20
cmake --preset clang-23
```

### GCC

Configure and build:

```bash
cmake --preset gcc-14
cmake --build --preset gcc-14
```

Available presets:

```bash
cmake --preset gcc-14
cmake --preset gcc-17
cmake --preset gcc-20
cmake --preset gcc-23
```

### MSVC

Configure and build:

```bash
cmake --preset msvc-14
cmake --build --preset msvc-14
```

Available presets:

```bash
cmake --preset msvc-14
cmake --preset msvc-17
cmake --preset msvc-20
cmake --preset msvc-23
```

### MinGW GCC

Configure and build:

```bash
cmake --preset mingw-14
cmake --build --preset mingw-14
```

Available presets:

```bash
cmake --preset mingw-14
cmake --preset mingw-17
cmake --preset mingw-20
cmake --preset mingw-23
```

## Release Builds

The provided Clang, GCC and MinGW presets use the `Debug` configuration.

To build a Release version, pass the configuration explicitly:

```bash
cmake --build --preset gcc-20 --config Release
```

For MSVC:

```bash
cmake --build --preset msvc-20 --config Release
```

## Clean Build

To remove generated build files, delete the corresponding build directory and configure the project again.

For example:

```bash
cmake --fresh --preset gcc-20
cmake --build --preset gcc-20
```




