cmake_minimum_required(VERSION 3.10)

# Set the project name
project(HelloRaylib C)

# Specify the C standard
set(CMAKE_C_STANDARD 11)
set(CMAKE_C_STANDARD_REQUIRED True)

# Include directories
include_directories(include)

# Library directories
link_directories(lib)

# Add the executable
add_executable(main main.c )

# Link raylib and other necessary frameworks
target_link_libraries(main
    ${CMAKE_SOURCE_DIR}/lib/libraylib.a
    "-framework CoreVideo"
    "-framework IOKit"
    "-framework Cocoa"
    "-framework GLUT"
    "-framework OpenGL"
)

# Optionally, you can set the compiler explicitly if needed
set(CMAKE_C_COMPILER /Library/Developer/CommandLineTools/usr/bin/cc)