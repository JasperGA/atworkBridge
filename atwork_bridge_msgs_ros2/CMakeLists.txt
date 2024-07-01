cmake_minimum_required(VERSION 3.8)
project(atwork_commander_msgs)

if(CMAKE_COMPILER_IS_GNUCXX OR CMAKE_CXX_COMPILER_ID MATCHES "Clang")
    add_compile_options(-Wall -Wextra -Wpedantic)
endif()

find_package(ament_cmake REQUIRED)
find_package(geometry_msgs REQUIRED)
find_package(std_msgs REQUIRED)
find_package(nav_msgs REQUIRED)
find_package(rosidl_default_generators REQUIRED)
#find_package(rosidl_generate_interfaces REQUIRED)
find_package(builtin_interfaces REQUIRED)

rosidl_generate_interfaces(${PROJECT_NAME}

  #TODO SEPERATE INTO CLASSIFICATIONS AND ADD HEADINGS
  "msg/Object.msg"
  "msg/ObjectTask.msg"
  "msg/RefboxState.msg"
  "msg/RobotHeader.msg"
  "msg/RobotState.msg"
  "msg/Task.msg"
  "msg/Transport.msg"
  "msg/Workstation.msg"
  "msg/Jog.msg"
  "msg/SudoControl.msg"
  "msg/Alignment.msg"


  "srv/GenerateTask.srv"
  "srv/TaskOpt.srv"
  "srv/ArmBrain.srv"
  "srv/ArmControl.srv"
  "srv/Navigation.srv"
  "srv/PositionInCamera.srv"
  "srv/PickAndPlace.srv"
  "srv/StartTargetBroadcast.srv"
  "srv/StopTargetBroadcast.srv"
  "srv/GetInventoryState.srv"
  "srv/PlaceItemInventory.srv"
  "srv/PickItemInventory.srv"
  "srv/GetItemId.srv"
  "srv/GetItemName.srv"
  "srv/GetItemInformation.srv"
  "srv/OrTools.srv"
  "srv/GiveBrainList.srv"
  "srv/NavAlignment.srv"
  DEPENDENCIES geometry_msgs builtin_interfaces std_msgs nav_msgs # Add packages that above messages depend on, in this case geometry_msgs for Sphere.msg

 )

ament_package()
