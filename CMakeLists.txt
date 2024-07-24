cmake_minimum_required(VERSION 3.12)
project(3dRenderDemo)

set(CMAKE_CXX_STANDARD 17)

find_package(OpenGL REQUIRED)
find_package(glfw3 REQUIRED)

find_package(glm REQUIRED)

include_directories(${OPENGL_INCLUDE_DIR})
include_directories(${CMAKE_CURRENT_SOURCE_DIR}/include)

add_executable(${PROJECT_NAME} 
    src/main.cpp
    src/glad.c
)

target_link_libraries(${PROJECT_NAME} 
    ${OPENGL_LIBRARIES}
    glfw
    glm::glm
)

file(COPY ${CMAKE_SOURCE_DIR}/shaders DESTINATION ${CMAKE_BINARY_DIR})
