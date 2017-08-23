include_directories("../include")
include_directories("../examples/common")
include_directories("${PROJECT_BINARY_DIR}/generated")

file(GLOB test_SRC
    "*.h"
    "*.cc"
)

# Enable C++ conformance under MSVC
add_compile_options($<$<CXX_COMPILER_ID:MSVC>:/permissive->)

#all_tests
add_executable(all_tests ${test_SRC})
set_target_properties(all_tests PROPERTIES FOLDER tests)
target_link_libraries(all_tests sc2api sc2lib sc2utils)
