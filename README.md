# Lua but built with CMake!
The Lua toolkit is a toolkit to create things. I built it with CMake so it becomes cross-platform

## How to build

The only thing to do is to run:

```bash
    # for Unix, I prefer you use Makefiles
    mkdir -p build
    cd build
    cmake .. -G "Unix Makefiles"
    make
```

```batch
    rem for Windows
    if not exist build mkdir build
    cd build
    rem In fact, I prefer that you build the project with these 2 systems in Windows
    rem For MinGW:
    cmake -G "MinGW Makefiles"
    mingw32-make
    rem Or use:
    make
    rem For Visual Studio:
    cmake ..
    rem NOTE: CMake will configure VS as default target, so you can just use:
    cmake --build . --config Release
```

But if you wanna install it, just target CMake building to ```install```