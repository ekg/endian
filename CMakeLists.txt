cmake_minimum_required(VERSION 3.10)
project(endian)

# Define library
add_library(endian INTERFACE)
target_compile_features(endian INTERFACE cxx_std_11)
target_include_directories(endian INTERFACE include/)

# Install headers
install(
  DIRECTORY ./include
  DESTINATION ${CMAKE_INSTALL_PREFIX}/include
  FILES_MATCHING
  PATTERN *.hpp)

