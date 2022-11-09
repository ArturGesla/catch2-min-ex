
cmake_minimum_required(VERSION 3.10)

set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

project(rotst VERSION 1.0)

# add_subdirectory("/people/gesla/Documents/git/Catch2/build")

# set (Catch2_DIR "/people/gesla/Documents/git/Catch2/build" )
# # add_subdirectory(./Catch2)
# find_library(Catch2 REQUIRED NAMES libCatch2Main.a PATHS "/people/gesla/Documents/git/Catch2/build/lib")

# message (STATUS "catch found at: ${Catch2}")

# # These tests can use the Catch2-provided main

# add_executable(tests test.cpp)
# # target_include_directories(tests PUBLIC "/people/gesla/Documents/git/Catch2/src/*")
# link_directories("/people/gesla/Documents/git/Catch2/build/lib")
# target_link_libraries(tests PUBLIC ${Catch2})

# target_include_directories(tests PUBLIC "/people/gesla/Documents/git/Catch2/build/include/catch2")
# target_include_directories(tests PUBLIC "/people/gesla/Documents/git/Catch2/build/include/")
# target_include_directories(tests PUBLIC "/people/gesla/Documents/git/Catch2/build/lib")

# set(Catch2_DIR "/people/gesla/Documents/git/Catch2/build")
set(CMAKE_PREFIX_PATH "/people/gesla/Documents/git/Catch2/build/")
set(CMAKE_FIND_DEBUG_MODE TRUE)
find_package(Catch2 REQUIRED CONFIG PATHS "/people/gesla/Documents/git/Catch2/build/lib/cmake/Catch2/" ) # like find lib but searches for additional headers using Config.cmake files
add_executable(tests test.cpp)
target_link_libraries(tests PRIVATE Catch2::Catch2WithMain)
