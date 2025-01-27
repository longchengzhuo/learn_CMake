add_subdirectory(common)
add_subdirectory(sub)
add_subdirectory(add)
add_subdirectory(calculator)

add_executable(lesson4_1 main.cpp)
target_link_libraries(lesson4_1 calculator)