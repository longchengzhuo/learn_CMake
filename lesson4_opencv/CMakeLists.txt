find_package(OpenCV REQUIRED)
add_executable(lesson4_opencv main.cpp)
target_include_directories(lesson4_opencv PRIVATE ${OpenCV_INCLUDE_DIRS})
TARGET_LINK_LIBRARIES(lesson4_opencv ${OpenCV_LIBS})
# 电脑如何知道OpenCV_INCLUDE_DIRS和OpenCV_LIBS分别是什么呢？
# 猜测：在通过brew install opencv的时候，在系统环境变量中，注入了/opt/homebrew/Cellar/opencv/4.11.0/lib/cmake/opencv4/OpenCVConfig.cmake相关的路径
# 在OpenCVConfig.cmake中定义了相关路径的具体内容
# 通过find_package去具体的找