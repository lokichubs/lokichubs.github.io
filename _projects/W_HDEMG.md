---
layout: page
title: High Density Electromyography (HDEMG) Sensor
description: Designed and built a 64 electrode array with 2mm spacing to pick up motor neuron activity from surface myography. Also built headstage with bio-signal amplifiers for the same to enable data readout. 
img: assets/img/HDEMG_cover.png
importance: 2
category: work
---

The project is part of a larger effort to develop and validate a system for rapidly and comfortably diagnosing disorders of motor unit function in facial muscles:

1. Identify nature of disorder (degeneration, hyperactivity)
2. Localize anatomical site of disorder
3. Monitor changes after treatment

My work revolved around designing and testing the hardware for the same. I developed the Sensor array and myo headstage in the system diagram below. 

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/HDEMG_sys_diagram.png" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    System Diagram
</div>

I designed an 8x8 electrode array with 2mm spacing with holes in between to allow for simulatenous use of under the skin electrodes.

<div class="row justify-content-sm-center">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/HDEMG_tile_kicad.png" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/HDEMG_cover.png" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Left depicts Kicad design for array and right depicts manufactured product
</div>

I also designed a 64 pin headstage that would interface with the HDEMG tile to allow for data readout. 

<div class="row justify-content-sm-center">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/HDEMG_headstage_kicad.png" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/HDEMG_headstage_prod.png" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Left depicts Kicad design for headstage and right depicts manufactured product
</div>

Then we proceeded with testing. The mean channel RMS was 6.36 uV with an standard deviation of around 1.11 uV across the RMS channel values. The lowest SNR was around 20db, prooving high signal quality. 

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/HDEMG_snr.png" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Signal to Noise Ratio histogram across all channels
</div>

I was the first subject on the device and it showed smooth rainbow waterfall trends when I was smiling - successfully picking ip motor neuron activity.

<div class="row justify-content-sm-center">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/HDEMG_waterfall.png" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/HDEMG_subject_0.png" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Left depicts waterfall graph for open smile and Right depicts subject 0 smiling (me)
</div>

Further more the device allows for discrimination of motor units (MU) on the face with clear signal propogation accross channels below on a 20 uV scale

<div class="row justify-content-sm-center">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/HDEMG_MU1.png" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/HDEMG_MU3.png" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Left MU 1,Right MU3
</div>

Orderly recruitment of distinct motor units prooved to be observable as well.

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/HDEMG_spike_train.png" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Spike train graph across 80 seconds and 5 motor units (for two smile iterations)
</div>

Innervation sites identifiable using channels with greatest peak-2-peak amplitudes with motor unit action potentials. 

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/HDEMG_innervation.png" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Innervation sites heatplot motor units 
</div>

However Spread of MU innervation sites should become more distinct as electrode spacing increases. Current work includes building a 4x4 mm spacing tile for the same.