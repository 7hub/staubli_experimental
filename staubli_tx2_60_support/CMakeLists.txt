cmake_minimum_required(VERSION 3.8)
project(staubli_tx2_60_support)

if(CMAKE_COMPILER_IS_GNUCC OR CMAKE_CXX_COMPILER_ID MATCHES "Clang")
  add_compile_options(-Wall -Wextra -Wpedantic)
endif()

find_package(ament_cmake REQUIRED)
find_package(rclpy REQUIRED)
ament_export_dependencies(${THIS_PACKAGE_INCLUDE_DEPENDS})

#Install
install(
  DIRECTORY config launch meshes urdf rviz
  DESTINATION share/staubli_tx2_60_support
)

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

ament_package()

# if (CATKIN_ENABLE_TESTING)
#   find_package(roslaunch REQUIRED)
#   roslaunch_add_file_check(tests/roslaunch_test_tx2_60.xml)
#   roslaunch_add_file_check(tests/roslaunch_test_tx2_60l.xml)
# endif()

# install(DIRECTORY config launch meshes urdf
#   DESTINATION ${CATKIN_PACKAGE_SHARE_DESTINATION})

