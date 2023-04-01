cmake_minimum_required(VERSION 3.21.0)

project(CrashRemedy VERSION 0.0.1)

# Disable this to have the console.
#set(OPTIONS WIN32)

#set(CMAKE_EXPORT_COMPILE_COMMANDS ON)

set(CMAKE_C_STANDARD_REQUIRED 11)
set(CMAKE_CXX_STANDARD 20)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

set(CMAKE_CXX_FLAGS "-m64 -march=westmere -mtune=generic -fno-rtti -fno-exceptions -Wall -Wextra -Wno-unused-function -Werror=return-type -g -gcodeview")
set(CMAKE_C_FLAGS "-m64 -march=westmere -mtune=generic -Wall -Wextra -Werror=return-type -g -gcodeview")
set(CMAKE_EXE_LINKER_FLAGS "-Wl,--pdb=")

add_compile_definitions(NOMINMAX)

find_path(GLFW_INCLUDE_PATH REQUIRED NO_DEFAULT_PATH)
include_directories(${GLFW_INCLUDE_PATH})
find_path(GLFW_LIB_PATH REQUIRED NO_DEFAULT_PATH)
link_directories(${GLFW_LIB_PATH})

add_executable(CrashRemedy
	main.cpp
)

target_link_libraries(CrashRemedy PRIVATE libglfw3.a)
