include_directories(../../include)

add_library(
  pqueue

  OBJECT

  pqueue.c
)

if(ENABLE_TESTS)
add_executable(
  pqueue_test

  pqueue_test.c

  $<TARGET_OBJECTS:test_support>
)

target_link_libraries(pqueue_test ssl crypto)
add_dependencies(all_tests pqueue_test)
endif()
