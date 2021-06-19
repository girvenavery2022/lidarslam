How to launch and visualize lidarslam as of now

Open 3 terminals and source them 

In the first terminal launch mammoth by using:
	ros2 launch mammoth_gazebo mammoth.launch.py
	
In the second terminal, launch lidarslam by using:
	ros2 launch lidarslam lidarslam.launch.py
	
In the third terminal launch lidarslams rviz by using:
	rviz2 -d src/lidarslam_ros2/lidarslam/rviz/mapping.rviz 

In lidarslams rviz, trick it into using sensor_msg/msg/PointCloud2 
as the type for the modified_map by adding a PointCloud2 and setting the topic to /map
drive mammoth around and wait until the scanmatcher starts publishing pointclouds.

After the scanmatcher publishes map data, add another PointCloud2 and set the topic to /modified_map
disable the map pointcloud and drive mammoth around until graph_base_slam publishes PointCloud data
