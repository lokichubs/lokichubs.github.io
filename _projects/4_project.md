---
layout: page
title: Safety Printed Circuit Board (PCB) for Direct Current (DC) distribution panel
description: A project that involved the design, manufacturing, and installation of a custom PCB
img: assets/img/PCB_3D_Model.png
importance: 4
category: work
---

This project revolved around designing, manufacturing, and installing a PCB that can be sent a control input using a raspberry pi. The project aims to turn on or turn off a 480 V source depending on a 5 V control signal. 

<div class="row justify-content-sm-center">
    <div class="col-sm-4 mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/PCB_Sketch.png" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm-8 mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/PCB_Switch.png" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Left displays the sketch/concept for the PCB. Right displays the switch that needs to be turned on or off based on control logic (red box - power input, green box - switch control)
</div>

First, the circuit was tested on a bread board with a LED light prior to installation. Once verified, a circuit schematic was drawn into EasyEDA and KiCAD

<div class="row justify-content-sm-center">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/PCB_Testing.png" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/PCB_Circuit.png" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Left shows the testing to identify the MOSFET required for the circuit to operate. Right shows the resulting circuit mapped to EasyEDA/KiCad
</div>

After this, the gerber was created with the appopriate parts chosen and was manufactured through JLCPB and installed in house

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/PCB_Gerber.png" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/PCB_BOM.png" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>

<div class="caption">
    Top Shows the gerber diagram and bottom shows the Bill of Materials (BOM) for the same
</div>






