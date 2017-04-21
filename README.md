# heron
# wp1 ERIAN
The file is for the clearpath heron boat.

The rep is specially for Clearpath Heron USV(umanned surface vessel)
Operating system requirement

First you should have the same operating system which should be the same with Heron onboard PC, so the ubuntu 12.04 LTS and Hydro ROS OP should be installed properly.
The packages you need to install for successfully Catkin_make in heron_ws workspace

Even you've follow the Hydro ROS installation instruction online, you should also follow up the user manual for Heron.

In the command line: sudo apt-get install ros-hydro-kingfisher-desktop

copy the files in heron_ws/src to some workspace which you build on your pc, then cd into your workspace and catkin_make, you may get some error for the cmake,then

sudo apt-get install ros-hydro-(the package which you need,such like roslint,nmea_msgs or nmea-msgs,control_toolbox or control-toolbox,and anything else)
The further README will state more clearly abiut the ROS structure for Heron
20/02/2017 Edit

When you want to roslaunch the base.launch, you may get some error which warns you to install some other packages needed. and remember, you may use the ros-hydro-A-B to install the A_B package which is included in the error.So pay attention to the subscript.

What's more, when you wanna roslaunch the describtion.launch you maybe should change the xacro:if value="false" to replace value="0" to eliminate the error that prompts during the roslaunch.

And I have changed the the base.launch content: from to pkg="robot_pose_ekf", since I can not locate the robot_pose-ekf_gpsfix package when i tried :sudo apt-get install ros-hydro-robot_pose_ekf_gpsfix.

Also we need to change the static_tf for base_footprint to baselink, or it will not publish the odom frame even it get the navfat/fix topic.
