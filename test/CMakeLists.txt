include_directories(BEFORE ${PROJECT_SOURCE_DIR})

add_executable(test_jwt testjwt.cpp)
add_test(jwt test_jwt)

if (UNIX)
    target_link_libraries(test_jwt jwt crypto)
elseif(WIN32)
    target_link_libraries(test_jwt jwt crypt32 libcrypto ws2_32)
endif()