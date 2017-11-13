cmake_minimum_required(VERSION 3.3.2)

project(kde2
        VERSION 2.2.2
        LANGUAGES C CXX)

include(GNUInstallDirs)

set(_projects Qt2)
macro(find_package)
    if(NOT "${ARGV0}" IN_LIST _projects)
        _find_package(${ARGV})
    endif()
endmacro()

add_subdirectory(qt2)
add_subdirectory(kdelibs)
