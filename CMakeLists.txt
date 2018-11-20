cmake_minimum_required(VERSION 3.1)
project(game.libretro.beetle-saturn)

list(APPEND CMAKE_MODULE_PATH ${PROJECT_SOURCE_DIR})

find_package(Kodi REQUIRED)
find_library(BEETLE-SATURN_LIB NAMES mednafen_saturn_libretro${CMAKE_SHARED_LIBRARY_SUFFIX} PATH_SUFFIXES libretro)

set(BEETLE-SATURN_CUSTOM_BINARY ${BEETLE-SATURN_LIB}
    ${PROJECT_NAME}${CMAKE_SHARED_LIBRARY_SUFFIX})

build_addon(${PROJECT_NAME} BEETLE-SATURN "")

include(CPack)
