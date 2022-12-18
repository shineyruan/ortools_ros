cmake_minimum_required(VERSION 3.18)
project(ortools_ros)

# Set compile options
if(NOT CMAKE_CXX_STANDARD)
  set(CMAKE_CXX_STANDARD 20)
  set(CMAKE_CXX_STANDARD_REQUIRED ON)
  set(CMAKE_CXX_EXTENSIONS OFF)
endif()
if(CMAKE_COMPILER_IS_GNUCXX OR CMAKE_CXX_COMPILER_ID MATCHES "Clang")
  add_compile_options(-Wall -Wextra -Wpedantic -Wno-unused-parameter -Wno-unused-variable)
endif()

# find dependencies
find_package(ament_cmake_auto REQUIRED)
ament_auto_find_build_dependencies()

# build lib
option(BUILD_absl "" ON)
option(BUILD_Protobuf "" ON)
option(BUILD_re2 "" ON)
option(BUILD_Eigen3 "" OFF)
option(BUILD_CoinUtils "" ON)
option(BUILD_Osi "" ON)
option(BUILD_Clp "" ON)
option(BUILD_Cgl "" ON)
option(BUILD_Cbc "" ON)
option(BUILD_HIGHS "" ON)
option(BUILD_SCIP "" ON)
option(BUILD_SAMPLES "" OFF)
option(BUILD_EXAMPLES "" OFF)
add_subdirectory(or-tools)

# export lib
ament_export_libraries(ortools)

if(BUILD_TESTING)
  find_package(ament_lint_auto REQUIRED)
  # the following line skips the linter which checks for copyrights
  # comment the line when a copyright and license is added to all source files
  set(ament_cmake_copyright_FOUND TRUE)
  # the following line skips cpplint (only works in a git repo)
  # comment the line when this package is in a git repo and when
  # a copyright and license is added to all source files
  set(ament_cmake_cpplint_FOUND TRUE)
  ament_lint_auto_find_test_dependencies()
endif()

ament_auto_package()
