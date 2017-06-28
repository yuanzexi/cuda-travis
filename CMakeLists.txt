# basic setup for cmake
cmake_minimum_required(VERSION 3.1 FATAL_ERROR)
set(CMAKE_INCLUDE_CURRENT_DIR ON)
set(CMAKE_INCLUDE_DIRECTORIES_PROJECT_BEFORE ON)
set(CMAKE_COLOR_MAKEFILE ON)
set(CMAKE_CXX_STANDARD_REQUIRED True)
set(CMAKE_CXX_STANDARD 11)
# disable in source builds
# this is only a temporary fix, but for now we need it as cmake will
# otherwise overwrite the existing makefiles
set(CMAKE_DISABLE_SOURCE_CHANGES ON)
set(CMAKE_DISABLE_IN_SOURCE_BUILD ON)

#
# PROJECT is QUDA
#
project("HELLO" VERSION 0.9.0)

  find_package(CUDA REQUIRED)
  set(USING_CUDA_LANG_SUPPORT False)

cuda_add_executable(hello hello.cu)