# BiFusHNet

**BiFusHNet: Bilateral Feature Fusion with Hexagonal Attention for Robust Saliency Detection under Uncertain Environments**

This repository is reserved for the official implementation of the proposed **BiFusHNet** framework.  

> 🔧 **Note:** The code is currently undergoing an organization process and will be made available to the research community soon. Stay tuned for updates.

---

## 📋 Table of Contents
- [Introduction](#introduction)
- [Method Overview](#method-overview)
- [Network Architecture](#network-architecture)
- [Datasets](#datasets)
- [Installation](#installation)
- [Results](#results)
- [Citation](#citation)
- [License](#license)
- [Contact](#contact)

---

## 📌 Introduction

Saliency detection plays a foundational role in many vision tasks such as segmentation, object detection, and image captioning. In this work, we propose **BiFusHNet**, a novel saliency detection network designed to perform robustly under **visual uncertainties** and **dynamic environments**.

The framework addresses challenges like:
- Preserving fine object boundaries
- Handling noisy inputs and visual ambiguities
- Maintaining high performance across diverse real-world scenarios

---

## 🔍 Method Overview

BiFusHNet leverages bilateral feature fusion and a novel hexagonal attention mechanism to enhance discriminative feature representation. The architecture is tailored to preserve fine object boundaries while maintaining robustness to noise and visual ambiguities.

Key contributions include:
- **Bilateral Feature Fusion**: Effectively integrates low-level and high-level features
- **Hexagonal Attention Mechanism**: Captures contextual information with geometric precision
- **Uncertainty Modeling**: Explicitly handles visual uncertainties for more robust predictions

> Full architectural details, along with module breakdowns and additional ablation studies, will be available soon.

---

## 🔄 Network Architecture
Visual Illustration of the proposed network.
![BiFusHNet Architecture](Network.png)



## 📂 Datasets

BiFusHNet is trained and evaluated on several widely used saliency detection benchmarks. Below are the links to download each dataset:

- [DUTS](http://saliencydetection.net/duts/)  
- [DUT-OMRON](http://saliencydetection.net/dut-omron/)  
- [HKU-IS](https://i.cs.hku.hk/~gbli/deep_saliency.html)  
- [PASCAL-S](https://www.yanweifu.com/cvpr2014/)  
- [SOD](http://elderlab.yorku.ca/SOD/)  
- [ECSSD](https://www.cse.cuhk.edu.hk/leojia/projects/hsaliency/)  

Please organize the datasets in the following directory structure:

```
datasets/
├── Training/
│   └── DUTS-TR/
│       ├── images/
│       └── masks/
└── Evaluation/
    ├── DUTS-TE/
    │   ├── images/
    │   └── masks/
    ├── HKU-IS/
    │   ├── images/
    │   └── masks/
    ├── DUT-OMRON/
    │   ├── images/
    │   └── masks/
    ├── PASCAL-S/
    │   ├── images/
    │   └── masks/
    ├── SOD/
    │   ├── images/
    │   └── masks/
    └── ECSSD/
        ├── images/
        └── masks/
```

---

## 🛠️ Installation


# Clone the repository
git clone https://github.com/username/BiFusHNet.git
cd BiFusHNet


## 📊 Results

We present a comprehensive empirical analysis of BiFusHNet with state-of-the-art comparison across six benchmark datasets. Our evaluation includes four key metrics (F-measure, MAE, E-measure, and S-measure) to provide a thorough assessment of performance. The quantitative results demonstrate the effectiveness of our uncertainty modeling approach, while qualitative visualizations highlight our method's superior boundary preservation and robustness to visual ambiguities. These extensive experiments enable researchers to make fair and informed comparisons with our approach.

| Method | DUTS-TE |  |  |  | DUT-OMRON |  |  |  | HKU-IS |  |  |  |
|--------|---------|---------|---------|---------|---------|---------|---------|---------|---------|---------|---------|---------|
|        | F^max | MAE | E_m | S_m | F^max | MAE | E_m | S_m | F^max | MAE | E_m | S_m |
| BiFusHNet (w/o uc) | 0.895 | 0.028 | 0.948 | 0.904 | 0.814 | 0.045 | 0.900 | 0.859 | 0.939 | 0.024 | 0.970 | 0.928 |
| BiFusHNet (w/ uc) | 0.901 | 0.026 | 0.952 | 0.910 | 0.820 | 0.043 | 0.903 | 0.864 | 0.944 | 0.023 | 0.971 | 0.933 |

| Method | PASCAL-S |  |  |  | SOD |  |  |  | ECSSD |  |  |  |
|--------|---------|---------|---------|---------|---------|---------|---------|---------|---------|---------|---------|---------|
|        | F^max | MAE | E_m | S_m | F^max | MAE | E_m | S_m | F^max | MAE | E_m | S_m |
| BiFusHNet (w/o uc) | 0.879 | 0.052 | 0.921 | 0.874 | 0.861 | 0.082 | 0.882 | 0.821 | 0.950 | 0.026 | 0.967 | 0.935 |
| BiFusHNet (w/ uc) | 0.881 | 0.050 | 0.924 | 0.880 | 0.859 | 0.083 | 0.884 | 0.832 | 0.948 | 0.026 | 0.970 | 0.939 |

Or

| Method | Dataset | F^max | MAE | E_m | S_m |
|--------|---------|-------|-----|-----|-----|
| BiFusHNet (w/o uc) | DUTS-TE | 0.895 | 0.028 | 0.948 | 0.904 |
| BiFusHNet (w/ uc) | DUTS-TE | 0.901 | 0.026 | 0.952 | 0.910 |
| BiFusHNet (w/o uc) | DUT-OMRON | 0.814 | 0.045 | 0.900 | 0.859 |
| BiFusHNet (w/ uc) | DUT-OMRON | 0.820 | 0.043 | 0.903 | 0.864 |
| BiFusHNet (w/o uc) | HKU-IS | 0.939 | 0.024 | 0.970 | 0.928 |
| BiFusHNet (w/ uc) | HKU-IS | 0.944 | 0.023 | 0.971 | 0.933 |
| BiFusHNet (w/o uc) | PASCAL-S | 0.879 | 0.052 | 0.921 | 0.874 |
| BiFusHNet (w/ uc) | PASCAL-S | 0.881 | 0.050 | 0.924 | 0.880 |
| BiFusHNet (w/o uc) | SOD | 0.861 | 0.082 | 0.882 | 0.821 |
| BiFusHNet (w/ uc) | SOD | 0.859 | 0.083 | 0.884 | 0.832 |
| BiFusHNet (w/o uc) | ECSSD | 0.950 | 0.026 | 0.967 | 0.935 |
| BiFusHNet (w/ uc) | ECSSD | 0.948 | 0.026 | 0.970 | 0.939 |

### Quantitative Results

![Quantitative Results](Quan1.png)
![Quantitative Results](Quan2.png)


### Qualitative Results

![Qualitative Results](Comp.png)


We provide saliency predictions (Visual Results) generated by **BiFusHNet** on all evaluation datasets:

🔗 [Download Saliency Maps (Google Drive)](https://drive.google.com/drive/folders/1XAL7ikHMQiB0CvrE0c7R664Ttna2c1mF?usp=sharing)


---

## 📝 Citation
Please cite our below published studies
```bibtex
@article{khan2025bilateral,
  title={Bilateral Feature Fusion with hexagonal attention for robust saliency detection under uncertain environments},
  author={Khan, Habib and Usman, Muhammad Talha and Koo, JaKeoung},
  journal={Information Fusion},
  pages={103165},
  year={2025},
  publisher={Elsevier}
}
```

---

## 📜 License

This project is licensed under the **MIT License** - see the [LICENSE](LICENSE) file for details.

---

## 📫 Contact

For questions, suggestions, or collaborations, feel free to open an issue or reach out via email habibkhan@ieee.org.
