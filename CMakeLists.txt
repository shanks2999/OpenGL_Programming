cmake_minimum_required(VERSION 3.10)
project(OpenGL_Programming)

#set(CMAKE_CXX_STANDARD 11)

set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -std=c++11")
add_executable(OpenGL_Programming ${PROJECT_SOURCE_DIR}/src/Application.cpp)


find_package (PkgConfig REQUIRED)
find_package (OpenGL REQUIRED)
#find_package (glfw3 REQUIRED)
include_directories("${PROJECT_SOURCE_DIR}/src" "${PROJECT_SOURCE_DIR}/Dependencies/GLFW/include" "${PROJECT_SOURCE_DIR}/Dependencies/GLEW/include")
link_directories("${PROJECT_SOURCE_DIR}/Dependencies/GLFW/lib-mingw-w64" "${PROJECT_SOURCE_DIR}/Dependencies/GLEW/lib/Release/x64")
target_link_libraries (OpenGL_Programming
        ${GLFW3_LIBRARY}
        ${OPENGL_LIBRARIES}
        ${GLEW_LIBRARY}
        ${COCOA_LIBRARY} ${COREVID_LIBRARY} ${IOKIT_LIBRARY}
        "${PROJECT_SOURCE_DIR}/Dependencies/GLFW/lib-mingw-w64/glfw3.dll" "${PROJECT_SOURCE_DIR}/Dependencies/GLEW/lib/Release/x64/glew32s.lib")

#target_link_libraries (OpenGL_Programming
#        ${OPENGL_LIBRARIES} glfw3 glew32s glu32 opengl32)
#target_link_libraries(OpenGL_Programming "${PROJECT_SOURCE_DIR}/Dependencies/GLFW/lib-mingw-w64/libglfw3dll.a" "${PROJECT_SOURCE_DIR}/Dependencies/GLEW/lib/Release/x64/glew32s.lib")
#target_link_libraries(ProjectName ../windows/system/user32)
#add_library(myLogicalExtLib SHARED IMPORTED src/Application.cpp)
#set_target_properties(myLogicalExtLib PROPERTIES IMPORTED_LOCATION "Dependencies/GLFW/lib-mingw-w64/")
