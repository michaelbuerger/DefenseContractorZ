cmake_minimum_required(VERSION 3.10)

# set project name
project(DefenseContractorZ)

# specify the C++ standard (note alt. for Windows)
set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED True)

add_subdirectory(GLEngine)

# find all source files
file (GLOB_RECURSE source_files "src/*.cpp")
# add executable
add_executable(DefenseContractorZ ${source_files})

target_link_libraries(DefenseContractorZ PUBLIC GLEngine)
target_include_directories(GLEngine PUBLIC
    ./include/
    ./GLEngine/include
    ./GLEngine/spdlog-1.9.2/include/
    ./GLEngine/glew-2.1.0/include/
    ./GLEngine/glfw/include/
    ./GLEngine/CPPML/include/
    ./GLEngine/imgui/include/
)
# goal is to eliminate need for most of these includes in top-level game