---
layout: page
title: Power Over Ethernet (POE) Lighting System Implementation
description: Designed and deployed a Direct Current (DC) lighting system. Determined new system uses 20% less energy on larger scales compared to AC Lighting systems using custom built current data aquicition system based on R-Pi. (Led to my first lead author publication)
img: assets/img/publication_preview/Publication_Preview_Lighting.png
importance: 7
category: work
related_publications: true
---

The project revolved around implementing a DC Lighting system with devices from <a href='https://www.poetexas.com'>PoE Texas</a> in a residential space with Direct Current (DC) distribution panel. First the key components needed to be installed in the system.

<div class="row justify-content-sm-center">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/POE_KS.png" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/POE_Light.png" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Left is the Kinetic Switch (KS) which served as the wireless input for the control system. Right is the DC light which served as the actuator for the system.
</div>

<div class="row justify-content-sm-center">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/POE_Switch.png" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/POE_LInc.png" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
        <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/POE_CORTAP.png" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Left is the PoE Switch which redirects controls and power through the circuit.Middle is the LINC which serves as the node point for each room in the residential space. Right is the CORTAP which served as the controls hub for the entire system
</div>

Once this was obtained, each device needed to be uniquely labeled and installed in the first floor. The unique ID process allowed for automation of the entire control system. 

<div class="row justify-content-sm-center">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/POE_Setup.png" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/POE_Controls.png" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Left is the schematic made to uniquely identify and install lights on the first floor. Right is the controls hub used to configure the controls for the entire system
</div>

The next step involved testing the lighting system installation on different scales and relevant debugging prior to data collection. 

<div class="row justify-content-sm-center">
    <div class="col-sm-8 mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/POE_Small.png" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm-4 mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/POE_Large.png" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    The above shows the small and large scale installations from left to right
</div>

To compare the DC and the AC lighting system, a data acquisition system for the current was made and installed on the DC distribution panel. The system utlized and arudino,ACS 712 (a hobby current sensor), ADS1115 (analog to digital converter), and C++ code (will upload to github soon) to measure the current. Since the DC panel held a constant voltage, the power was then calculated using P=VI. 

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/POE_DAQ.png" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Circuit diagram/layout for the power data acquisition.
</div>

The first hand comparison of their power consumption showed that DC consumed more power than AC lighting systems for 1 room scale

<div class="row justify-content-sm-center">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/POE_AC.png" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/POE_DC.png" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    AC vs DC (Left and Right) power consumptions as a time series on the evening of 02/01/2024
</div>

However, scaling the power consumption to any room larger than one shows that DC lights are favorable

<div class="row justify-content-sm-center">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/POE_Scaling_Small.png" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/POE_Scaling_Large.png" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Scaling the power consumption to residential (Left) and Commercial Scales 
</div>

The images show that the DC Lighting PoE system is less efficient at a smaller scale. However, on a larger scale, the power savings can go up to 22%. 

Read my publication {% cite sriram2024development %} to learn more. 



