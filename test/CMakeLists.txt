include(FetchContent)
FetchContent_Declare(
  googletest
  URL https://github.com/google/googletest/archive/58d77fa8070e8cec2dc1ed015d66b454c8d78850.zip
)
FetchContent_MakeAvailable(googletest)

include_directories (${**PROJECT_NAME**_SOURCE_DIR}/src)

add_executable(
  **PROJECT_NAME**-test
  class1_test.cc
)

target_link_libraries(
  **PROJECT_NAME**-test
  Library1
  GTest::gtest_main
  GTest::gmock_main
)

include(GoogleTest)
gtest_discover_tests(**PROJECT_NAME**-test)