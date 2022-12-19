# ortools_ros

ROS 2 package mirror of Google OR-Tools

## Usage

In any `ament_cmake_auto` project, add the following line to package dependency:

```xml
  <depend>ortools_ros</depend>
```

and you're done!

For more detailed usage, check the ROS 2 package `ortools_ros_examples`.

## Note

This project by default only builds the C++ target with default CMake options and all necessary dependencies. Users could pass more build options (i.e., more solvers) to the project by using `colcon build --cmake-args -DBUILD_DEPS=ON`.

## Acknowledgements

- CI set up is borrowed from [autoware.universe](https://github.com/autowarefoundation/autoware.universe) and [autoware-github-actions](https://github.com/autowarefoundation/autoware-github-actions).
