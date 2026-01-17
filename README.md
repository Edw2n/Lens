# ADAPTIVE CAMERA SENSOR FOR VISION MODELS (ICLR 2025)
Inspired by how humans use corrective lenses to gain clearer vision rather than overtraining their brains, this work proposes *Lens*, a novel camera sensor control framework that captures high-quality inputs from the model's perspective. It enhances performance under distribution shifts without requiring retraining.

## Lens
[📄 Read the paper (ICLR 2025)](https://openreview.net/pdf?id=He2FGdmsas) (The code will be updated soon.)
<img align="center" src="https://raw.githubusercontent.com/Edw2n/Lens/main/lens-concept.png" width="800">
<img align="center" src="https://raw.githubusercontent.com/Edw2n/Lens/main/lens-overview.png" width="400">

---
## 📸 ImageNet-ES Diverse

**ImageNet-ES Diverse** is a benchmark dataset of **192,000 real-world images** captured with a physical camera in a controlled testbed (ES-Studio Diverse), under various sensor parameters and lighting conditions. It complements the original [ImageNet-ES](https://huggingface.co/datasets/Edw2n/ImageNet-ES) by introducing more diverse and realistic covariate shifts for robustness evaluation.
<img align="center" src="https://raw.githubusercontent.com/Edw2n/Lens/main/ImageNet-ES-Diverse-example.png" width="800">

  
### 🗂️ ImageNet-ES Diverse Strucuture
```
ImageNet-ES-Diverse
├── es-train (8K)
│   └── tin_no_resize_sample_removed 
│   # 8K original validation samples of Tiny-ImageNet without references in ImageNet-ES 
├── es-diverse-test (193K)
    ├── auto_exposure (30K)  = 1K * 6 environments *5 shots
    ├── param_control  (162K) = 1K * 6 environments * 27 shots
    └── sampled_tin_no_resize2 # reference samples (1K)
```
The main paper and the appendix detail the dataset specifications and present analyses on adaptive sensing and qualitative insights.

  
### 🎛️ ES-Studio Diverse
To address the limitations of existing robustness benchmarks, including *ImageNet-ES*, we customized *ES-Studio* into *ES-Studio Diverse* by replacing the reference display with printed images captured from a screen. While maintaining control over lighting and sensor parameters as in *ES-Studio*, this customized setup and broader lighting variations enable the collection of data that is complementary to *ImageNet-ES*.
<img align="center" src="https://raw.githubusercontent.com/Edw2n/Lens/main/ES-Studio-Diverse.png" width="350">
<img align="center" src="https://raw.githubusercontent.com/Edw2n/Lens/main/testbed-diverse-actual-.png" width="650">

  
### 🖥️ Download from terminal
To download the dataset directly from your terminal using **`wget`:**
```bash
wget https://huggingface.co/datasets/Edw2n/ImageNet-ES-Diverse/resolve/main/ImageNet-ES-Diverse.zip
```
---
### 📜 Citation

```bibtex
@inproceedings{
baek2025adaptive,
title={Adaptive Camera Sensor for Vision Models},
author={Eunsu Baek and Sung-hwan Han and Taesik Gong and Hyung-Sin Kim},
booktitle={The Thirteenth International Conference on Learning Representations},
year={2025},
url={https://openreview.net/forum?id=He2FGdmsas}
}
