# Perception System to identify the location of static objects with a monocular camera
The aim of the project is to improve the perception system of a mobile robot in order to identify the location of static objects to avoid collision, by limiting the sensor system.

![image](https://github.com/CatInTheRain/depth_estim-object_detect-monocular/assets/55113554/9508eeea-4d50-44ef-867c-f9bcaa96f5ed)

2D LiDAR is able to detect only the obstacle in its line of sight: location of low obstacles must be estimated through only a monocular camera.

## Depth Estimation
In this project depth estimation is carried out with an extended Kalman filter to reduce the computational load and in order that performance does not depend on the training dataset.
Dynamic nonlinear model takes into account the kinematics of the feature point (whose depth you want to estimate) resolved in the camera coordinate frame of a unicycle **(1)** and the pinhole camera model **(2)**.

![image](https://github.com/CatInTheRain/depth_estim-object_detect-monocular/assets/55113554/3a032f09-81ce-433d-992a-3bba790e51d7)


![image](https://github.com/CatInTheRain/depth_estim-object_detect-monocular/assets/55113554/b4518546-1293-4937-bf6f-ec1d87498692)

Process model

![image](https://github.com/CatInTheRain/depth_estim-object_detect-monocular/assets/55113554/73804a31-7d83-4584-a640-c11906434bf4)

Measurement model

![image](https://github.com/CatInTheRain/depth_estim-object_detect-monocular/assets/55113554/b5dddd6e-c4b2-4e15-820b-294ec1040e9f)

Simulation of depth estimation of one chess corner with EKF
![image](https://github.com/CatInTheRain/depth_estim-object_detect-monocular/assets/55113554/bf0f8660-c163-42bb-87b8-9cc1e407be65)

https://github.com/CatInTheRain/depth_estim-object_detect-monocular/assets/55113554/2b1981fb-938d-4f21-80b7-78716ede0c67

![image](https://github.com/CatInTheRain/depth_estim-object_detect-monocular/assets/55113554/637904ff-b8a2-461a-9798-881cb647ada5)

## Object Detection Algorithm
This algorithm aims to detect and classify the edges of generic objects that are not in the line of sight of the LiDAR.

![image](https://github.com/CatInTheRain/depth_estim-object_detect-monocular/assets/55113554/2c33d0f5-13d1-418d-b42c-738f8c39e2b1)

![image](https://github.com/CatInTheRain/depth_estim-object_detect-monocular/assets/55113554/5a8591bc-e0e3-48c3-9458-15f37d71aaec)

Then lines are tracked and associated to a common object through Histogram (HSV) Intersection Algorithm, while the unicycle moves. 

https://github.com/CatInTheRain/depth_estim-object_detect-monocular/assets/55113554/05615583-bd3f-405a-bbc1-35accb7c1fd2


This is the final result

https://github.com/CatInTheRain/depth_estim-object_detect-monocular/assets/55113554/8e6a142c-d7cb-4521-b627-016803e57935

https://github.com/CatInTheRain/depth_estim-object_detect-monocular/assets/55113554/1a17de9f-d56c-4b0d-a95a-3d1f0d7ea1f6


## Bibliography

- Mansour, Mostafa, et al. "Depth estimation with ego-motion assisted monocular camera." Gyroscopy and Navigation 10.3 (2019): 111-123.
- Bresenham, Jack E. "Algorithm for computer control of a digital plotter." IBM Systems journal 4.1 (1965): 25-30
- Sabatini, Stefano, et al. "Vision-based pole-like obstacle detection and localization for urban mobile robots." 2018 IEEE Intelligent Vehicles Symposium (IV). IEEE, 2018.
- Swain, Michael J., and Dana H. Ballard. "Color indexing." International journal of computer vision 7.1 (1991): 11-32.

The complete report and code are available and can be requested in private.
