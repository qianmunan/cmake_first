cmake_minimum_required(VERSION 3.0.0)
project(test1)

aux_source_directory(./ SRC)
include_directories(${HEADPATH})
link_directories(${LIBPATH})
link_libraries(${CALCLIB})
set(EXECUTABLE_OUTPUT_PATH ${EXECPATH})
# 查找fmt库并启用fmt链接
find_package(fmt REQUIRED)
find_package(GTest REQUIRED)

add_executable(${APPNAME1} ${SRC})
include_directories(${GTEST_INCLUDE_DIRS})

target_link_libraries(${APPNAME1} ${GTEST_BOTH_LIBRARIES} pthread)
# 链接fmt库，无需指定库的路径
target_link_libraries(${APPNAME1} PRIVATE fmt::fmt)
