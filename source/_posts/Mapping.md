title: RealSense D435+T265 Occupancy Grid Mapping
author: Wen-Yu Chien
categories:
  - Penn State PURL
tags:
  - SLAM
  - RealSense
  - Mapping
  - Localization
  - OpenGL
  - ImGUI
date: 2020-08-31 20:33:25
---
Following videos show the demo of the real-time voxel grid mapping on-board. I built the whole environment including the walls, FOV, trajectories and GUI in OpenGL myslef. The GUI make the colaboration with another team in Virgina Tech easier. No ROS in this whole project. For more details, please check the specs down below the page.
***
## Apartment scan test:
This video shows the indoor real-time mapping in first personal view. Due to COVID-19, I cannot enter the lab/hangar and had to film it in my apartment with hand-carry test. The white grid plane shows the specific layer of the 2D map on the top left corner.

<iframe width="560" height="315" src="https://www.youtube.com/embed/TYZf3p9I-Iw" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

***
## Hangar flight test: 
This video was filmed earlier before the pandemic. The top right corners shows the sceen on the ground station. The communication protocal is using non-block UDP socket to send the map and camera pose to reconstruct the 3D scene.

<iframe width="560" height="315" src="https://www.youtube.com/embed/6d41JG6h2XI" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

***
#### Hardward

<!--more-->
<figure>
    <img src="https://www.rutronik.com/fileadmin/Rutronik/Supplier/Intel/NUC/Compressed_Nuc_Boards.png" width="600px" alt="IntelNUC" align=center>
	<figcaption>Computer: Intel 8th-gen i7 NUC</figcaption>
</figure>

<figure>
	<img src="https://cdn.shopify.com/s/files/1/0253/9057/9791/products/3d-robotics-pixhawk_1024x1024.jpg?v=1594492105" width="300px" alt="Pixhawk" align=center>
	<figcaption>Flight Computer/Controller: Pixhawk(PX4)</figcaption>
</figure>

<figure>
	<img src="https://res.cloudinary.com/rsc/image/upload/b_rgb:FFFFFF,c_pad,dpr_1.0,f_auto,h_337,q_auto,w_600/c_pad,h_337,w_600/F1720981-03?pgw=1" width="300px" alt="RealSenseD435" align=center>
	<figcaption>Intel® RealSense™ D435 Depth Camera for Mapping</figcaption>
</figure>
<figure>
<img src="https://www.intelrealsense.com/wp-content/uploads/2019/02/intel_realsense_tracking_camera_photo_angle_1_675x450.png" width="300px" alt="RealSenseD435" align=center>
	<figcaption>Intel® RealSense™ T265 Tracking Camera for Localization
</figcaption>
</figure>

***
#### Software
* 2D Visualization: OpenCV</br>
* 3D Visualization: OpenGL3, GLAD gl loader, 
* Graphical User Interface: ImGUI(connection status, map infromation, pose information) (No other 3D engine)</br>
* Camera API: librealsense</br>
* Communication: C++ socket UDP: send pose and map to path planning and flight controller</br>

***
#### Algorithm & Math
1. Line Tracing
2. Inverse Sensor Model
3. Logodd
4. MinDist Filter
5. Distance Weighting Compensator
6. Map Shift Interface: to make the map expandable/moveable with the camera/vehicle
***
#### Fixed Size Map
* Frame Coordinates: Same as D435
* Ground True Dimension: 20 x 6 x 20 m^3
* Grid Dimension: 100 x 30 x 100 cells
* Cell Size: 0.2m^3 / cell
* Bounding Dimension: 1 x 1 x 1 m for expandable map.
***

More details: [Wen-Yu Chien's Thesis PDF file]( https://etda.libraries.psu.edu/catalog/18031wuc188)