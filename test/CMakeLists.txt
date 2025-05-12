file(GLOB_RECURSE TEST_FILES RELATIVE ${CMAKE_CURRENT_SOURCE_DIR} *.cpp)

find_package(Catch2 REQUIRED)

# Create test executable
add_executable(do_tests main.cpp ${TEST_FILES})

target_link_libraries(do_tests PRIVATE 
    Catch2::Catch2WithMain  
    rl_engine
)

# Add test
add_test(NAME do_tests COMMAND do_tests)