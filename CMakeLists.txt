cmake_minimum_required(VERSION 3.7)
project(gtkt)

set(CMAKE_C_STANDARD 99)

set(SOURCE_FILES main.c)

find_package(PkgConfig REQUIRED)
pkg_check_modules(GTK3 REQUIRED gtk+-3.0)

include_directories(${GTK3_INCLUDE_DIRS})
link_directories(${GTK3_LIBRARY_DIRS})

add_definitions(${GTK3_CFLAGS_OTHER})

add_executable(gtkt ${SOURCE_FILES})
target_link_libraries(gtkt "gtk-win32-3.0.lib" "gobject-2.0.lib" "glib-2.0.lib" "libmysql")