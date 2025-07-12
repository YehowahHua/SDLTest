cmake_minimum_required(VERSION 3.30)
project(SDL-test)

set(CMAKE_CXX_COMPILER g++)

set(CMAKE_CXX_STANDARD 23)
set(CMAKE_CXX_STANDARD_REQUIRED YES)
set(CMAKE_CXX_EXTENSIONS OFF)

set(CMAKE_EXPERIMENTAL_CXX_IMPORT_STD ON)


# 包含目录
include_directories(
    ${CMAKE_SOURCE_DIR}/include
)

# 链接库路径
link_directories(${CMAKE_SOURCE_DIR}/lib)

# 可执行文件
add_executable(${PROJECT_NAME} src/main.cpp)

# 链接动态库
target_link_libraries(${PROJECT_NAME}
    SDL3 
)
target_link_libraries(${PROJECT_NAME}
    SDL3_image
)

# 拷贝库文件 文件
file(COPY ${PROJECT_SOURCE_DIR}/lib/SDL3.dll DESTINATION ${PROJECT_BINARY_DIR})
file(COPY ${PROJECT_SOURCE_DIR}/lib/SDL3_image.dll DESTINATION ${PROJECT_BINARY_DIR})