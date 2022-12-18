# ortools_ros

ROS 2 package mirror of Google OR-Tools

## Usage

Include this package in your `package.xml`:

```xml
<?xml version="1.0"?>
<?xml-model href="http://download.ros.org/schema/package_format3.xsd" schematypens="http://www.w3.org/2001/XMLSchema"?>
<package format="3">
  <name>ortools_ros_test</name>
  <version>0.0.0</version>
  <description>Test for Google OR-Tools ROS package</description>
  <maintainer email="shineyruan@gmail.com">Zhihao Ruan</maintainer>
  <license>Apache License 2.0</license>

  <buildtool_depend>ament_cmake_auto</buildtool_depend>

  <depend>ortools_ros</depend>

  <test_depend>ament_lint_auto</test_depend>
  <test_depend>ament_lint_common</test_depend>

  <export>
    <build_type>ament_cmake</build_type>
  </export>
</package>
```

Set up the normal `ament_cmake_auto` project:

```cmake
# find dependencies
find_package(ament_cmake_auto REQUIRED)
ament_auto_find_build_dependencies()

# build
ament_auto_add_executable(test_vrp src/test_vrp.cpp)
```

Include the headers as if from OR-Tools normal installation:

```c++
#include "ortools/constraint_solver/routing.h"
#include "ortools/constraint_solver/routing_enums.pb.h"
#include "ortools/constraint_solver/routing_index_manager.h"
#include "ortools/constraint_solver/routing_parameters.h"
```

and you're done!

## Note

This project by default only builds the C++ target with default CMake options and all necessary dependencies. Users could pass more build options (i.e., more solvers) to the project by using `colcon build --cmake-args -DBUILD_DEPS=ON`.

## Acknowledgements

- CI set up is borrowed from [autoware.universe](https://github.com/autowarefoundation/autoware.universe) and [autoware-github-actions](https://github.com/autowarefoundation/autoware-github-actions).
