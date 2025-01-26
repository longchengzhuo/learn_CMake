add_subdirectory(add)

include_directories(./lib)
link_libraries(libadd_static.a)
link_directories(/Users/chengzhuolong/CLionProjects/learn_CMake/lesson2_1/lib)

add_executable(lesson2_1 main.cpp ) # 这个位置只能放cpp文件，不能放库文件，想让编译器知道库文件在哪，需要使用link相关的指令
#target_link_libraries(lesson2_1 libadd_static.a)
# 这句话的target实际上就是lesson2_1这个东西