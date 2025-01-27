add_library(common_object OBJECT common.cpp)
#target_include_directories(common_object INTERFACE ./)
# 这个地方绝对不能使用第二行而不使用第五行
#CMake 的接口属性传递遵循以下规则：
#依赖链传递：属性只能通过 target_link_libraries 建立的依赖链传递
#物理合并 ≠ 逻辑依赖：直接使用对象文件（$<TARGET_OBJECTS>）属于物理层面的文件操作，不会触发属性传递
#目标隔离性：每个目标（common_object 和 common）是独立的实体，它们的属性作用域默认不相通
add_library(common STATIC $<TARGET_OBJECTS:common_object>)
target_include_directories(common INTERFACE ./)
