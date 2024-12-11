---
layout: page
title: Tight Learned Inetrial Odometry (TLIO) Data Loader
description: Utilized Machine Learning with traditional controls methods for current pose estimation for humanoid robot - Digit
img: assets/img/TLIO_project_image.png
importance: 1
category: work
---

The TLIO Data Loader Model focuses on creating a reliable dataloader for our motion capture (MOCAP) and Inertial Measurment Unit (IMU) data pipeline. 

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/TLIO_Flowchart.png" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Tight Learned Inertial Odometry (TLIO) Flowchart
</div>

Reinforcement Learning is used to determine the displacement estimates of the IMU at any point in time. Then an Extended Kalman Filter (EKF) was used to integrate the displacement and determine the roll, pitch, and yaw. 

Data collection using the MOCAP, IMU, and Treadmill was conducted as shown below for 30 different motion profiles:

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/TLIO_Digit Setup.png" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    The D-Flow,VICON Software, and Digit robot used to capture the experimental data to be fed into model
</div>

<div class="row justify-content-sm-center">
    <div class="col-sm-8 mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/TLIO_IMU_Sample.png" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm-4 mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/TLIO_Calibration.png" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Left depicts the device used to calibrate the MOCAP Cameras. Right depicts the software to calibrate the IMU
</div>

Once the data was collected, It needed to be transformed to match the format required for the TLIO network and EKF. The main problem was data incompletness - A lack of readings directly from the MOCAP system such as the acceleration and angular velocity. A <a href="https://github.com/lokichubs/TLIO-Data-Loader">Custom Data Loader</a> with smoothing, integration, and derivation functionalities was made. 

Once transformed, the IMU and MOCAP data needed to be time aligned, interpolated, and calibrated using external JSON files. The entire process was automated to ensure replaceability. The results are as follows:

<div class="row justify-content-sm-center">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/TLIO_Pre Loader.png" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/TLIO_Post Loader.png" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Left depicts raw IMU and MOCAP Data for data set 01 and the Right depicts the same processed for the TLIO
</div>

To debug the model, a learning curve plotting function was added to the train file

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/TLIO_epoch_33.png" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/TLIO_epoch_66.png" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/TLIO_epoch_99.png" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Learning curve for 33,66,and 99 epochs for data set 05 (left to right)
</div>

The model was then trained on the same data and tested with different train-test-val batches. Both were 60%-20%-20% splits - one was a random choice and the other had a train set which was filled with the complex motion profiles.

<div class="row justify-content-sm-center">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/TLIO_random.png" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/TLIO_specific.png" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Left depicts test result of random split and Right depicts test result of specific split for data set 05
</div>

As seen above the model for which train data was handpicked shows only around a drift of ~20 cm in either direction whereas the random train data set shows ~50 cm drift


