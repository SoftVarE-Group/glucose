cmake_minimum_required(VERSION 3.12)

project(glucose VERSION 3.0)

option(BUILD_SHARED_LIBS OFF "Whether to build a shared (instead of static) library.")

set(ZLIB_USE_STATIC_LIBS ON)

find_package(ZLIB REQUIRED)

include_directories(${CMAKE_CURRENT_SOURCE_DIR})
include_directories(${ZLIB_INCLUDE_DIRS})

add_library(glucose
    core/Solver.cc
    simp/SimpSolver.cc
    utils/Options.cc
    utils/System.cc
)

target_link_libraries(glucose ZLIB::ZLIB)

add_executable(binary EXCLUDE_FROM_ALL simp/Main.cc)
set_target_properties(binary PROPERTIES OUTPUT_NAME glucose)
target_link_libraries(binary glucose)
