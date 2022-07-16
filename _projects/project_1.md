---
layout: page
title: FPGA accelerator for semantic segmentation
description: Accelerating Sparse Neural Networks for Semantic Image Segmentation on FPGA platforms
img: assets/img/segmentation_fc_motivation.png
importance: 1
category: work
---

From healthcare to autonomous driving, Deep Neural Networks (DNN) dominate over the traditional Computer Vision (CV) approaches in terms of accuracy and efficiency. Exponential increase of DNN applications require tremendous computation power of underlying hardware resources. Naturally the superior performance of DNN models comes at a cost of huge memory footprint and complex calculations. Even if Graphics Processing Units (GPU) are the main work-horse during the training of DNNs for their massive computational capabilities, they are not suitable for mobile deployments. Computations in remote cloud is also not suitable for unreliable network latency and potential security issues. The hardware, accelerating the inference at edge should offer flexibility of deployment due to the rapid-changing nature of this research area. Field-programmable Gate Array (FPGA) provides the best trade-off between performance, power-consumption and design flexibility.

<div class="row">
<div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/segmentation_fc_motivation.png" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>

</div>
<div class="caption">
A simple FCN network consisting of only convolutional layers, taking
an image as input and gives a semantic segmented image with
pixel-wise classification as output.
</div> 

CNN being the de-facto framework for computer vision, semantic image segmentation is one of the most complex tasks providing pixel-wise annotations for complete scene understanding. For a critical application like autonomous driving, DeepLabV3+ model provides the state-of-the-art Mean Intersection-Over-Union (mIOU) on CityScapes dataset. In this work, a fully pipelined hardware accelerator implementing novel dilated convolution was introduced. Using this accelerator, an end-end  DeepLabV3+ deployment was possible on FPGA. This architecture exploits hardware optimizations like 3-D loop unrolling, memory tiling to maximize use of computational resources and provides 2.34X latency improvement with respect to the baseline architecture.

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/7donlyimage.png" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/pruning.png" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>

</div>
<div class="caption">
    On the left, A simple Convolutional Layer with strided Convolution. A 4-D weight tensor is required to produce 3-D ouput feature maps from a 3-D input
feature map. Right, Classification of Pruning depending on granularity of weight kernels.
</div>


Further, a Genetic Algorithm (GA) based automated channel pruning technique was used to jointly optimize hardware usage and model accuracy. Finally, hardware awareness was incorporated in the pruning search by hardware heuristics and an accurate model of the custom accelerator. Overall a 4X latency improvement was observed for a sacrifice of 4% of mIOU.

<!-- To give your project a background in the portfolio page, just add the img tag to the front matter like so:

    ---
    layout: page
    title: project
    description: a project with a background image
    img: /assets/img/12.jpg
    --- -->



<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/arria10_fpga_kit.jpg" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    An FPGA development kit with functional flexibility suitable for
hardware prototyping
</div>

The findings and development details of the accelerator has been compiled here and the paper based on this work has recently been published at **DAC 2022**.

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/semantic_demo.png" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Qualitative results for HW aware pruned models on different scenarios
in the CityScapes dataset. Black regions are unlabeled in the original
dataset.
</div>




<!-- The code is simple.
Just wrap your images with `<div class="col-sm">` and place them inside `<div class="row">` (read more about the <a href="https://getbootstrap.com/docs/4.4/layout/grid/">Bootstrap Grid</a> system).
To make images responsive, add `img-fluid` class to each; for rounded corners and shadows use `rounded` and `z-depth-1` classes.
Here's the code for the last row of images above: -->

<!-- {% raw %}
```html
<div class="row justify-content-sm-center">
    <div class="col-sm-8 mt-3 mt-md-0">
        {% include figure.html path="assets/img/6.jpg" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm-4 mt-3 mt-md-0">
        {% include figure.html path="assets/img/11.jpg" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
```
{% endraw %} -->
