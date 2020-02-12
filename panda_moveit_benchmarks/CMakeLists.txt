cmake_minimum_required(VERSION 2.8.3)
project(panda_moveit_benchmarks)
find_package(catkin REQUIRED)

catkin_package()


#############
## Install ##
#############
set(LAUNCH_DIRS
  launch/
)
set(MODEL_DIRS
)
set(WORLD_DIRS
)
foreach(dir ${LAUNCH_DIRS})
  install(DIRECTORY ${dir}/
    DESTINATION ${CATKIN_PACKAGE_SHARE_DESTINATION}/${dir})
endforeach(dir)

#############
## Testing ##
#############
if (CATKIN_ENABLE_TESTING)
  find_package(roslaunch REQUIRED)
  roslaunch_add_file_check(launch/)
endif()
