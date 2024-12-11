---
layout: page
title: Custom Data Power Acquisition System Using Hobby Electronics
description: A project that replicates expensive power acquisition systems' accuracy at a lower price
img: assets/img/publication_preview/Publication_Preview_PZEM.png
importance: 3
category: work
related_publications: true
---

This project revolves around creating a power data accquisition system (DAQ) using a the PZEM printed circuit board. It it can measure power when connected directly to the breaker.

<div class="row justify-content-sm-center">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/PZEM_PCB.png" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/PZEM_Connection_Layout.png" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    The PCB of the PZEM (Left) and the connection to the breaker system
</div>

The microcontroller used was the ESP32. C++ was used to process the data and establish serial communication. The main issue was that ESP32 operated on 3.3 V logic and the PZEM operated on 5V logic. Hence a level shifter was needed as per the diagram shown below

<div class="row justify-content-sm-center">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/PZEM_Level_Shifter_Circuit.png" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/PZEM_Level_Shifter.png" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    The circuit diagram (left) and the PCB for the level shifter (right)
</div>

Prior to installation in the breaker box, a 3D model was made in NX seimens to verify the dimensions

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/PZEM_3D_Model.png" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    3D model for designed data acquisition system
</div>

Post installation, our custom DAQ was compared with IoTWatt for accuracy and it yielded very positive results

<div class="row justify-content-sm-center">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/PZEM_Graph_1.png" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/PZEM_Graph_2.png" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    PZEM vs Iotwatt power measurements as a time series for two different breakers
</div>

We then compared the price and error of the custom DAQ with respect to the IotWatt - we found that our DAQ was significantly cheaper for a marginal error

<div class="caption">
    Table with error and cost comparison results
</div>
<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/PZEM_Results.png" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>

Read my publication {% cite farha2023design %} to learn more.

