---
layout: page
title: Project - Minutes 
description: A project that aims to create a personal assistant using machine learning methods and computer vision (if you know you know)
img: assets/img/MINS_cover.jpeg
importance: 1
category: fun
---

This projects revolves around creating a personal assitant that can help facilitate physical tasks. The first challenge I thought I'd tackle is a facial recognition activated door Lock. 

To achieve this I utilized a Siamese Neural Network (SNN),from this <a href='https://www.cs.cmu.edu/~rsalakhu/papers/oneshot1.pdf'>paper</a>. 

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/MINS_example.png" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Examples of what the SNN can be used to to achieve
</div>

The training data, and later the real time data, was acquired using the OpenCV Library (and my rather mediocre webcam).The embedding layer,which used relu,the custom distance layer, and model was setup using Pytorch. The pipeline can be seen below.

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/MINS_Transform.png" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Convolutional architecture utlized by the SNN
</div>

Below are some of the results after multiple debug and training attempts - showcasing the ability to differentiate my face from others. (Although, the model did prove to be slightly racist at times lol)

<div class="row justify-content-sm-center">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/MINS_Neg.jpeg" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/MINS_Pos.jpeg" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Left is an example of the SNN negative output and the right is the SNN positive output.
</div>

Once the model was trained, and verified, I wrote some code in python using the Kivy library to setup an app that would allow facial recognition from the phone. The following are example results from the project

<div class="row justify-content-sm-center">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/MINS_Case_open.jpeg" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/MINS_Case_open_fail.jpeg" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Left is an example of when the door would be unlocked. Right is when it would remain locked (R.I.P Akira Toriyama Sensei)
</div>

Will get the github-repo for the same up soon!
