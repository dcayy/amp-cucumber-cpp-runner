set(CMAKE_COMPILE_WARNING_AS_ERROR On)

add_executable(cucumber_cpp.acceptance_test ${CCR_EXCLUDE_FROM_ALL})

target_link_libraries(cucumber_cpp.acceptance_test PRIVATE
    cucumber_cpp
    cucumber_cpp.runner
    cucumber_cpp.acceptance_test.hooks
    cucumber_cpp.acceptance_test.steps
)

add_executable(cucumber_cpp.acceptance_test.custom ${CCR_EXCLUDE_FROM_ALL})

target_sources(cucumber_cpp.acceptance_test.custom PRIVATE
    MainCustom.cpp
)

target_link_libraries(cucumber_cpp.acceptance_test.custom PRIVATE
    cucumber_cpp
    cucumber_cpp.acceptance_test.hooks
    cucumber_cpp.acceptance_test.steps
)

add_subdirectory(hooks)
add_subdirectory(steps)
