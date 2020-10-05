add_subdirectory(googletest)

# some function to easily add tests
function(addTest TEST_NAME TEST_SOURCE)
  add_executable(${TEST_NAME} ${TEST_SOURCE})
  target_link_libraries(${TEST_NAME} gtest_main)
  add_test(${TEST_NAME} ${TEST_NAME}) # simply add args if you need some
endfunction()

include_directories(./googletest/googletest/)

# the tests
addTest(SomeTest SomeTest.cpp)