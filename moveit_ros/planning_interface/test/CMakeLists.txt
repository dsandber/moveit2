if(BUILD_TESTING)
  find_package(moveit_resources REQUIRED)
  find_package(ament_cmake_gtest REQUIRED)
  # TODO(henningkayser): migrate to launch_test find_package(rostest REQUIRED)
  find_package(eigen_conversions REQUIRED)

  # add_executable(test_cleanup test_cleanup.cpp)
  # target_link_libraries(test_cleanup moveit_move_group_interface)

  ament_add_gtest(moveit_cpp_test moveit_cpp_test.test moveit_cpp_test.cpp)
  # ament_target_dependencies(moveit_cpp_test rclcpp)
  target_link_libraries(moveit_cpp_test moveit_cpp)

  # TODO(henningkayser): re-enable new tests
  # add_rostest_gtest(move_group_interface_cpp_test
  # move_group_interface_cpp_test.test move_group_interface_cpp_test.cpp)
  # target_link_libraries(move_group_interface_cpp_test
  # moveit_move_group_interface ${catkin_LIBRARIES}
  # ${eigen_conversions_LIBRARIES})
  #
  # add_rostest_gtest(move_group_pick_place_test move_group_pick_place_test.test
  # move_group_pick_place_test.cpp)
  # target_link_libraries(move_group_pick_place_test moveit_move_group_interface
  # ${catkin_LIBRARIES} ${eigen_conversions_LIBRARIES})
  #
  # add_rostest_gtest(moveit_cpp_test moveit_cpp_test.test moveit_cpp_test.cpp)
  # target_link_libraries(moveit_cpp_test moveit_cpp ${catkin_LIBRARIES})
  #
  # add_rostest_gtest(subframes_test subframes_test.test subframes_test.cpp)
  # target_link_libraries(subframes_test moveit_move_group_interface
  # ${catkin_LIBRARIES} ${eigen_conversions_LIBRARIES})
endif()
