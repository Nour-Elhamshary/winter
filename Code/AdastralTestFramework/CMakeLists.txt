ad_cmake_init()

include(FetchContent)

# Get the name of this folder as the project name
get_filename_component(PROJECT_NAME ${CMAKE_CURRENT_SOURCE_DIR} NAME_WE)

ad_create_target(STATIC_LIBRARY ${PROJECT_NAME})

target_link_libraries(${PROJECT_NAME} PUBLIC godot::cpp)

if(MSVC)
  target_compile_options(${PROJECT_NAME} PRIVATE /W4 /WX)
endif()
