add_library(calculator STATIC calculator.cpp)
target_link_libraries(calculator PRIVATE add sub)
target_include_directories(calculator PUBLIC ../add)
# 把add文件夹这个路径告诉自己，同时告诉所有链接到calculator静态库的文件这个路径
# 具体来说，就是告诉calculator.cpp和main.cpp:你们的头文件寻找路径还要加上"../add"