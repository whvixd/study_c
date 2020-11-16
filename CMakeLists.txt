# refer:https://blog.csdn.net/afei__/article/details/81201039
# cmake 是一个跨平台、开源的构建系统。它是一个集软件构建、测试、打包于一身的软件。它使用与平台和编译器独立的配置文件来对软件编译过程进行控制。
cmake_minimum_required(VERSION 3.8) # 版本号
project(study_c) # 项目名称

# 头文件目录
INCLUDE_DIRECTORIES(
        include
)

# 指定资源文件
AUX_SOURCE_DIRECTORY(
        src DIR_SRCS
)

set(CMAKE_C_STANDARD 99)
set(SOURCE_FILES src/main.c include/number_utill.h src/number_util.c)

SET(NUMBER_UTIL
        ${DIR_SRCS}
)
add_executable(${PROJECT_NAME} ${SOURCE_FILES} ${NUMBER_UTIL}) # 生成可执行文件

TARGET_LINK_LIBRARIES(${PROJECT_NAME} m)
#add_library(common STATIC util.cpp) # 生成静态库
#add_library(common SHARED util.cpp) # 生成动态库或共享库