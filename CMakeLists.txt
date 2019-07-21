cmake_minimum_required(VERSION 3.14)
project(KLib "C")

function(onefilelib libname)
    add_library(${libname} STATIC ${libname}.c)
    target_compile_options(${libname} PRIVATE -Wall -Wextra -Werror)
    target_include_directories(${libname} PUBLIC ${CMAKE_CURRENT_SOURCE_DIR})
endfunction(onefilelib)

add_library(klibs INTERFACE)
target_include_directories(klibs INTERFACE ${CMAKE_CURRENT_SOURCE_DIR})

