cmake_minimum_required(VERSION 3.0.0)
project(gtest)


set(GTEST_ROOT usr/src/gtest)
find_package(GTest REQUIRED)

# 编译目标文件
add_executable(test_myapp main.cc)

# 链接 gtest 库
target_link_libraries(test_myapp GTest::GTest GTest::Main)
