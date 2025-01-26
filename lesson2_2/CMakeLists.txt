add_subdirectory(add)
include_directories(bin)
add_executable(lesson2_2 main.cpp)
target_link_libraries(lesson2_2 /Users/chengzhuolong/CLionProjects/learn_CMake/lesson2_2/bin/libadd_shared.dylib)