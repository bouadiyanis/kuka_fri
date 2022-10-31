cmake_minimum_required(VERSION 3.1.0)
project(kuka_fri)

# Default to C99
if(NOT CMAKE_C_STANDARD)
  set(CMAKE_C_STANDARD 99)
endif()

# Default to C++17
if(NOT CMAKE_CXX_STANDARD)
  set(CMAKE_CXX_STANDARD 17)
endif()

include_directories(src)

file(GLOB_RECURSE CORE_SOURCES src/kuka/*.c*)
add_library(${PROJECT_NAME} SHARED ${CORE_SOURCES})
install(TARGETS ${PROJECT_NAME}
  ARCHIVE DESTINATION lib
  LIBRARY DESTINATION lib
  RUNTIME DESTINATION bin
)

file(GLOB_RECURSE FRI_HEADERS src/kuka/fri/*.h)
install(FILES ${FRI_HEADERS}
  DESTINATION include/kuka/fri
)

file(GLOB_RECURSE PB_HEADERS src/kuka/pb/*.h)
install(FILES ${PB_HEADERS}
  DESTINATION include/kuka/pb
)

add_executable(kuka_fri_example src/example.cpp)
target_link_libraries(kuka_fri_example kuka_fri)