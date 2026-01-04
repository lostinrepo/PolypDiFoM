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

### Dataset Preparation
Download the polyp datasets and organize them as follows:
data/
├── TrainDB/ 
│ ├── images/
│ └── masks/
├── TestDB/
│ ├── CVC-300/
│ ├── CVC-ClinicDB/
│ ├── CVC-ColonDB/
│ ├── ETIS-LaribPolypDB/
│ └── Kvasir/

## Pre-trained Weights

We provide multiple pre-trained weight files corresponding to different configurations.  
The naming convention reflects which foundation models are used during training.

- **`unet_sam_dino_best.pth`**  
  Trained with **two foundation models**:
  - SAM
  - DINO  

- **`emcadnet_sam_dinov3_oneformer_3f.pth`**  
  Trained using **three integrated foundation models (3F setting)**:
  - SAM
  - DINOv3
  - OneFormer  

- **`pranet_sam_dino_oneformer_mask2.pth`**  
  Trained with **all integrated foundation models**:
  - SAM
  - DINO
  - OneFormer
  - Mask2Former

  (This model represents the **full configuration** and can be used to evaluate the overall performance of PolypDiFoM over PraNet.)

### 📥 Download Links

All pre-trained weights can be downloaded from Google Drive:

- [Download all model weights](https://drive.google.com/drive/folders/1yz92j-Ap2gkCvIPMBnxBldH7zvIV0UY4?usp=sharing)

## Code Organization and Usage

We provide a unified implementation file **`PolypDiFoM_UNetPP.ipynb`**, which contains the complete pipeline for the **U-Net++ architecture** under the **3-foundation-model (3F) setting**, integrating:

- SAM
- DINO
- OneFormer

This notebook includes the full workflow, covering:
- Dataset loading and preprocessing
- Feature generation from foundation models
- Model definition
- Training and evaluation procedures

### 🔹 Purpose of the Unified Notebook

The unified Jupyter notebook is provided to:
- Offer a **clear, end-to-end view** of the PolypDiFoM framework
- Help users easily understand the **overall training and inference flow**
- Enable straightforward replication of the proposed method

Researchers may **refactor the notebook into modular scripts** (e.g., `train.py`, `dataset.py`, `model.py`) according to their preferences or project structure.

---

### 🔹 Extending to Other Foundation-Model Settings

The same implementation can be **directly extended** to other configurations, such as:
- **2F** (e.g., SAM + DINO)
- **4F** (additional foundation models)

Feature extraction from SAM, DINO and OneFormer is explicitly presented in the notebook.  
Feature generation for other foundation models (e.g. Mask2Former, CLIP, I-JEPA etc. ) can be incorporated in a **similar manner**, allowing researchers to explore alternative combinations.

Currently, we evaluate PolypDiFoM using four foundation models which is already discussed in the papaer.  
The framework is **model-agnostic**, and users are encouraged to experiment with additional foundation models and suggest further improvements.

---

### 🔹 Paths and Weights

- All dataset and checkpoint paths in the notebook are **placeholders** and can be modified according to the user’s directory structure.
- Pre-trained weights can be included for **direct evaluation and testing**.

---

### 🔹 Future Updates

Additional notebooks corresponding to different foundation-model configurations (e.g., 2F and 4F settings) will be released after further code cleaning and modularization.



## Citation
If you find this work useful, please cite:

```bibtex
@article{agnihotri2025sam,
  title={From SAM to DINOv2: Towards Distilling Foundation Models to Lightweight Baselines for Generalized Polyp Segmentation},
  author={Agnihotri, Shivanshu and Majhi, Snehashis and Nayak, Deepak Ranjan and Jha, Debesh},
  journal={arXiv preprint arXiv:2512.09307},
  year={2025}
}
```

### License
This project is for research and educational purposes only.
Commercial use requires permission.










