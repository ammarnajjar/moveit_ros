set(MOVEIT_LIB_NAME moveit_lazy_free_space_updater)

add_library(${MOVEIT_LIB_NAME} src/lazy_free_space_updater.cpp)
set_target_properties(${MOVEIT_LIB_NAME} PROPERTIES COMPILE_FLAGS "${CMAKE_CXX_FLAGS} ${OpenMP_CXX_FLAGS}")
set_target_properties(${MOVEIT_LIB_NAME} PROPERTIES LINK_FLAGS "${OpenMP_CXX_FLAGS}")
target_link_libraries(${MOVEIT_LIB_NAME} moveit_occupancy_map_monitor ${catkin_LIBRARIES} ${Boost_LIBRARIES})

install(TARGETS ${MOVEIT_LIB_NAME} LIBRARY DESTINATION ${CATKIN_PACKAGE_LIB_DESTINATION})
install(DIRECTORY include/ DESTINATION include)
