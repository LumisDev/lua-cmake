cmake_minimum_required(VERSION 3.5)
project(Lua)

add_library(lualib STATIC 
    src/lapi.c 
    src/lcode.c 
    src/lctype.c 
    src/ldebug.c 
    src/ldo.c 
    src/ldump.c 
    src/lfunc.c 
    src/lgc.c 
    src/llex.c 
    src/lmem.c 
    src/lobject.c 
    src/lopcodes.c 
    src/lparser.c 
    src/lstate.c 
    src/lstring.c 
    src/ltable.c 
    src/ltm.c 
    src/lundump.c 
    src/lvm.c 
    src/lzio.c 
    src/lauxlib.c 
    src/lbaselib.c 
    src/lcorolib.c 
    src/ldblib.c 
    src/liolib.c 
    src/lmathlib.c 
    src/loadlib.c 
    src/loslib.c 
    src/lstrlib.c 
    src/ltablib.c 
    src/lutf8lib.c 
    src/linit.c)
target_include_directories(lualib PRIVATE include)
add_executable(lua src/lua.c)
target_include_directories(lua PRIVATE include)
target_link_libraries(lua PRIVATE lualib)
add_executable(luac src/luac.c)
target_include_directories(luac PRIVATE include)
target_link_libraries(luac PRIVATE lualib)
set_target_properties(lualib lua luac PROPERTIES
    ARCHIVE_OUTPUT_DIRECTORY "${CMAKE_BINARY_DIR}/bin"
    RUNTIME_OUTPUT_DIRECTORY "${CMAKE_BINARY_DIR}/bin"
)
install(FILES ${CMAKE_CURRENT_SOURCE_DIR}/include/lua.h ${CMAKE_CURRENT_SOURCE_DIR}/include/luaconf.h ${CMAKE_CURRENT_SOURCE_DIR}/include/lualib.h ${CMAKE_CURRENT_SOURCE_DIR}/include/lauxlib.h ${CMAKE_CURRENT_SOURCE_DIR}/include/lua.hpp DESTINATION include)
install(TARGETS lualib DESTINATION lib)
install(TARGETS lua luac DESTINATION bin)