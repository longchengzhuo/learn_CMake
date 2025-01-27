add_subdirectory(common)
add_subdirectory(sub)
add_subdirectory(add)
add_subdirectory(calculator)

add_executable(lesson3_1 main.cpp)
#target_include_directories(lesson3_1 PRIVATE ./calculator)
target_link_libraries(lesson3_1 calculator)