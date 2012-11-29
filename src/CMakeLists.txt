FIND_PACKAGE(Torch REQUIRED)
SET(src clocks.c core_profiler.c function_meter.c lua50_profiler.c stack.c)
SET(luasrc init.lua)

ADD_TORCH_PACKAGE(profiler "${src}" "${luasrc}" "Lua profiler")
TARGET_LINK_LIBRARIES(profiler luaT)

SUBDIRS(analyzer)
