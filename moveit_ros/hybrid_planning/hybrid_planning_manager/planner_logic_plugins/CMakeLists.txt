add_library(single_plan_execution_plugin SHARED src/single_plan_execution.cpp)
set_target_properties(single_plan_execution_plugin
                      PROPERTIES VERSION "${${PROJECT_NAME}_VERSION}")
ament_target_dependencies(single_plan_execution_plugin
                          ${THIS_PACKAGE_INCLUDE_DEPENDS})
target_link_libraries(single_plan_execution_plugin
                      moveit_hybrid_planning_manager)

add_library(replan_invalidated_trajectory_plugin SHARED
            src/replan_invalidated_trajectory.cpp)
set_target_properties(replan_invalidated_trajectory_plugin
                      PROPERTIES VERSION "${${PROJECT_NAME}_VERSION}")
ament_target_dependencies(replan_invalidated_trajectory_plugin
                          ${THIS_PACKAGE_INCLUDE_DEPENDS})
target_link_libraries(
  replan_invalidated_trajectory_plugin moveit_hybrid_planning_manager
  single_plan_execution_plugin)
