add_library(sub_object OBJECT sub.cpp)
target_link_libraries(sub_object PRIVATE common)
# 为什么要在这一步就把common链接到sub_object呢，为什么不能在第四行之后链接到sub呢
# 因为在把sub.cpp转化成sub_object.o的时候，得先生成sub.i，而这一步时就已经需要找到common.h了
add_library(sub STATIC $<TARGET_OBJECTS:sub_object> $<TARGET_OBJECTS:common_object>)
target_include_directories(sub INTERFACE ./)
