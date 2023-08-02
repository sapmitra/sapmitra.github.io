---
layout: post
title: Defended my Master Thesis on acceleration of semantic segmentation on FPGA
date: 2021-07-15 16:11:00-0400
inline: false
---


From healthcare to autonomous driving, Deep Neural Networks (DNN) dominate over the traditional Computer Vision (CV) approaches in terms of accuracy and efficiency. Exponential increase of DNN applications require tremendous computation power of the underlying hardware resources. Naturally, the superior performance of DNN models comes at a cost of huge memory footprint and complex calculations. Even if Graphics Processing Units (GPU) are the main work-horse during the training of DNNs for their massive computational capabilities, they are not suitable for mobile deployments. Computations in remote cloud is also not suitable for unreliable network latency and potential security issues. The hardware, accelerating the inference at the edge, should offer flexibility of deployment due to the rapid-changing nature of this research area. Field-programmable Gate Array (FPGA) provides the best trade-off between performance, power-consumption and design flexibility. Convolutional Neural Networks (CNN) are the state-of-the-art for computer vision applications. Semantic image segmentation is one of the most complex tasks in computer vision, providing pixel-wise annotations for complete scene understanding. For a critical application like autonomous driving, DeepLabV3+ model provides the state-of-the-art Mean Intersection-Over-Union (mIOU) for semantic segmentation on the CityScapes dataset. In this work, a fully pipelined hardware accelerator implementing novel dilated convolution was introduced. Using this accelerator, an end-end DeepLabV3+ deployment was possible on FPGA. This architecture exploits hardware optimizations like 3-D loop unrolling, memory tiling to maximize use of computational resources and provides 2.34 times latency improvement with respect to the baseline architecture. Further, a Genetic Algorithm (GA) based automated channel pruning technique was used to jointly optimize hardware usage and model accuracy. Finally, hardware awareness was incorporated in the pruning search by hardware heuristics and an accurate model of the custom accelerator. Overall a 4X speedup was observed for a 4% degradation in mIOU.

***

Thesis print available on mediaTUM: <a href="https://mediatum.ub.tum.de/1649493">Accelerating Semantic Image Segmentation on FPGA
</a>


***

Thesis Defense Video is here:
<iframe width="640" height="360" frameborder="0" src="https://mega.nz/embed/MGhAVDTL#qAPqJrRZrKYiOmxdRMeraDnHDVgAztD1KpmTX76SJbI" allowfullscreen ></iframe>

***

> Slides are available on request now.

***

