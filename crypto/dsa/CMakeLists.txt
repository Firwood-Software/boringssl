include_directories(../../include)

add_library(
  dsa

  OBJECT

  dsa.c
  dsa_asn1.c
)

if(ENABLE_TESTS)
add_executable(
  dsa_test

  dsa_test.c

  $<TARGET_OBJECTS:test_support>
)

target_link_libraries(dsa_test crypto)
add_dependencies(all_tests dsa_test)
endif()
