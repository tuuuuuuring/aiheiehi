cmake_minimum_required(VERSION 3.28)
project(mycode)

set(CMAKE_CXX_STANDARD 17)

# 需要添加查找OpenSSL，因为使用了HTTPS
find_package(OpenSSL REQUIRED)

find_package(workflow CONFIG REQUIRED)

add_executable(main main.cpp)

target_link_libraries(main
        PRIVATE
        workflow
        # 需要链接OpenSSL库
        OpenSSL::SSL
        OpenSSL::Crypto
)