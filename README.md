# From SAM to DINOv2: Towards Distilling Foundation Models to Lightweight Baselines for Generalized Polyp Segmentation

**Authors:**  
Shivanshu Agnihotri, Snehashis Majhi, Deepak Ranjan Nayak and Debesh Jha


## Framework Overview
Our framework integrates frozen foundation models (SAM, DINOv2, OneFormer and Mask2Former) into a lightweight segmentation baselines using a staged distillation strategy.

<p align="center">
  <img src="figures/framework.png" width="85%">
</p>

## Qualitative Results
Comparison of our method with state-of-the-art approaches on multiple polyp segmentation datasets.

<p align="center">
  <img src="figures/qualitative_results.png" width="90%">
</p>

## Method
-  Modular distillation that injects rich priors from multiple vision foundation models (SAM, DINOv2, CLIP, OneFormer, Mask2Former) into lightweight baselines (UNet/U-Net++).
-  Low- and high-frequency features are distilled into bottleneck layers.
-  A 3 phased training strategy ensures stable convergence.






