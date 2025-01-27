add_library(common STATIC common.cpp)
target_include_directories(common INTERFACE ./)
# 只把当前路径 暴露 给 链接到common的库。意味着凡是链接到common的库，他们的cmakelists中不需要再专门写include_directories了
# 相当于他们需要的头文件路径，已经打包进入common当中了，只要一链接common，就会得到 “./” 这个路径