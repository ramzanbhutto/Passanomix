cmake_minimum_required(VERSION 3.10)
project(Passanomix)

set(CMAKE_CXX_STANDARD 14)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

# find OpenSSL library
find_package(OpenSSL REQUIRED)

# Add executable
add_executable(password_manager main.cpp)

# link OpenSSL libraries
target_link_libraries(password_manager OpenSSL::SSL OpenSSL::Crypto)

# add compiler warnings
if(CMAKE_COMPILER_IS_GNUCXX OR CMAKE_CXX_COMPILER_ID MATCHES "Clang")
    target_compile_options(password_manager PRIVATE -Wall -Wextra -pedantic)
endif()
