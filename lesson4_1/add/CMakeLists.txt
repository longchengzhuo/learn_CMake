add_library(add_object OBJECT add.cpp)
target_link_libraries(add_object PRIVATE common) # 拿到common传递出来的头文件的位置
add_library(add STATIC $<TARGET_OBJECTS:add_object> $<TARGET_OBJECTS:common_object>)
target_include_directories(add INTERFACE ./)