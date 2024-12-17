
cmake_minimum_required(VERSION 3.27.0)

include("${CMAKE_CURRENT_LIST_DIR}/httpFilePaths.cmake")

add_library(free-rtos-core-http STATIC ${HTTP_SOURCES})

target_include_directories(free-rtos-core-http PUBLIC ${HTTP_INCLUDE_PUBLIC_DIRS})

target_compile_options(free-rtos-core-http PRIVATE
  -DHTTP_DO_NOT_USE_CUSTOM_CONFIG
  -DHTTP_USER_AGENT_VALUE="smart-vac-gauge"
  -Os
  -Wall
  -Wextra
  -Werror
  -Wno-unused-parameter
  -Wno-type-limits
)

