# Lua but built with CMake!
The Lua toolkit is a toolkit to create things. I built it with CMake so it becomes cross-platform

## How to build

The only thing to do is to run:

```bash
    # for Unix, I prefer you use Makefiles
    mkdir -p build
    cd build
    cmake .. -DLUA_BUILD_LIBRARY=ON -DLUA_BUILD_COMPILER=ON -DLUA_BUILD_INTREPRETER=ON
    # NOTE: CMake will configure Unix Makefiles as default target, so you can just use:
    make
```

```batch
    rem for Windows
    if not exist build mkdir build
    cd build
    rem In fact, I prefer that you build the project with these 2 systems in Windows
    rem For MinGW:
    cmake .. -DLUA_BUILD_LIBRARY=ON -DLUA_BUILD_COMPILER=ON -DLUA_BUILD_INTREPRETER=ON -G "MinGW Makefiles" 
    mingw32-make
    rem Or use:
    make
    rem For Visual Studio:
    cmake .. -DLUA_BUILD_LIBRARY=ON -DLUA_BUILD_COMPILER=ON -DLUA_BUILD_INTREPRETER=ON
    rem NOTE: CMake will configure VS as default target, so you can just use:
    cmake --build . --config Release
```

But if you wanna install it, just target CMake building to ```install```

## Options

The options used here are:
1. ```LUA_BUILD_INTREPRETER``` - for building the Lua interpreter. Default to ```ON```
2. ```LUA_BUILD_COMPILER``` - for building the Lua compiler. Default to ```ON```
3. ```LUA_BUILD_LIBRARY``` - for building the Lua library. Default to ```ON```
