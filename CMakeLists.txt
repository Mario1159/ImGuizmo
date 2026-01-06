cmake_minimum_required(VERSION 3.15)

project(imguizmo LANGUAGES CXX)

# TODO: Add support for building examples
# option(IMGUIZMO_BUILD_EXAMPLE "Build ImGuizmo example" OFF)

find_package(imgui REQUIRED)

add_library(imguizmo
    GraphEditor.cpp
    ImCurveEdit.cpp
    ImGradient.cpp
    ImGuizmo.cpp
    ImSequencer.cpp
)

add_library(imguizmo::imguizmo ALIAS imguizmo)

target_compile_features(imguizmo PUBLIC cxx_std_17)

target_include_directories(imguizmo
    PUBLIC
        ${CMAKE_CURRENT_SOURCE_DIR}
)

target_link_libraries(imguizmo
    PUBLIC
        imgui::imgui
)

# TODO: Add CMakeLists on example dir
#if (IMGUIZMO_BUILD_EXAMPLE)
#    add_subdirectory(example)
#endif()

