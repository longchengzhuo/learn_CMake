add_library(calculator_object OBJECT calculator.cpp)
target_link_libraries(calculator_object PRIVATE add sub)
add_library(calculator STATIC   $<TARGET_OBJECTS:calculator_object>
                                $<TARGET_OBJECTS:add_object>
                                $<TARGET_OBJECTS:sub_object>
                                $<TARGET_OBJECTS:common_object>)
target_include_directories(calculator PUBLIC ./)
# 把add文件夹这个路径告诉自己，同时告诉所有链接到calculator静态库的文件这个路径
# 具体来说，就是告诉calculator.cpp和main.cpp:你们的头文件寻找路径还要加上"../add"