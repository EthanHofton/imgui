cmake_minimum_required(VERSION 3.24.3)
project(imgui)

set(CMAKE_CXX_STANDARD 20)
set(CMAKE_CXX_STANDARD_REQUIRED TRUE)
set(CMAKE_EXPORT_COMPILE_COMMANDS ON)

set(IMGUI_SOURCES
    "imgui.cpp"
    "imgui_demo.cpp"
    "imgui_draw.cpp"
    "imgui_tables.cpp"
    "imgui_widgets.cpp")

set(IMGUI_BACKENDS
    "backends/imgui_impl_allegro5.cpp"
    "backends/imgui_impl_android.cpp"
    "backends/imgui_impl_dx10.cpp"
    "backends/imgui_impl_dx11.cpp"
    "backends/imgui_impl_dx12.cpp"
    "backends/imgui_impl_dx9.cpp"
    "backends/imgui_impl_glfw.cpp"
    "backends/imgui_impl_glut.cpp"
    "backends/imgui_impl_opengl2.cpp"
    "backends/imgui_impl_opengl3.cpp"
    "backends/imgui_impl_sdl.cpp"
    "backends/imgui_impl_sdlrenderer.cpp"
    "backends/imgui_impl_vulkan.cpp"
    "backends/imgui_impl_wgpu.cpp"
    "backends/imgui_impl_win32.cpp")

add_library(imgui ${IMGUI_SOURCES} ${IMGUI_BACKENDS})

# add include directory
target_include_directories(imgui PUBLIC ${CMAKE_CURRENT_SOURCE_DIR})
target_include_directories(imgui PUBLIC ${CMAKE_CURRENT_SOURCE_DIR}/backends)
