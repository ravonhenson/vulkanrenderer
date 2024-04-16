cmake_minimum_required(VERSION 3.27)
project(renderer)

set(CMAKE_CXX_STANDARD 17)

find_package(Vulkan REQUIRED)
find_package(GLFW3 REQUIRED)

add_executable(renderer main.cpp)
target_sources(renderer PRIVATE main.cpp)

target_link_libraries(renderer PRIVATE
        Vulkan::Vulkan
        glfw
)

# Include directories for GLM
find_package(glm REQUIRED) # GLM found by find_package if available
target_include_directories(renderer PRIVATE ${GLM_INCLUDE_DIRS})