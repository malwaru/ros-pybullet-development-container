cmake_minimum_required(VERSION 2.8.3)
project(youBot_placing_experiment)

find_package(catkin REQUIRED COMPONENTS
  rospy
  std_msgs
  trajectory_msgs
  geometry_msgs
)

catkin_python_setup()

catkin_package(
  CATKIN_DEPENDS
    rospy
    std_msgs
    geometry_msgs
    moveit_msgs
    moveit_commander
)

install(PROGRAMS
  ros/scripts/youBot_placing_node
  DESTINATION ${CATKIN_PACKAGE_BIN_DESTINATION}
)

#############
## Testing ##
#############

## Add gtest based cpp test target and link libraries
# catkin_add_gtest(${PROJECT_NAME}-test test/test_mcr_trajectory_saving.cpp)
# if(TARGET ${PROJECT_NAME}-test)
#   target_link_libraries(${PROJECT_NAME}-test ${PROJECT_NAME})
# endif()

## Add folders to be run by python nosetests
# catkin_add_nosetests(test)
