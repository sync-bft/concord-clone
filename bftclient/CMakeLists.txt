project (bftclient LANGUAGES CXX)

add_library(bftclient_new STATIC
  src/bft_client.cpp
  src/msg_receiver.cpp
  src/matcher.cpp
  src/quorums.cpp
)

target_include_directories(bftclient_new PUBLIC include)
target_include_directories(bftclient_new PUBLIC src)
target_link_libraries(bftclient_new PUBLIC bftcommunication bftheaders)

if (BUILD_TESTING)
    add_subdirectory(test)
endif()
