# 🌟 Super-Resolution Minimal Reproduction (SISR) 🌟

[![🐍 Python Version](https://img.shields.io/badge/Python-3.8+-blue.svg)](https://www.python.org/)
[![✨ Stars](https://img.shields.io/github/stars/Nuyoahwjl/SISR.svg)](https://github.com/Nuyoahwjl/SISR/stargazers)
[![📜 License](https://img.shields.io/badge/License-MIT-brightgreen.svg)](https://opensource.org/licenses/MIT)
[![🐛 Issues](https://img.shields.io/github/issues/Nuyoahwjl/SISR.svg)](https://github.com/Nuyoahwjl/SISR/issues)

🌈 **Demo Results** 🌈  
<img src="images/4.png" width="100%" alt="Demo Result 4"> 
<img src="images/5.png" width="100%" alt="Demo Result 5">
<img src="images/6.png" width="100%" alt="Demo Result 6"> 
<img src="images/7.png" width="100%" alt="Demo Result 7">
<img src="images/8.png" width="100%" alt="Demo Result 8"> 
<img src="images/9.png" width="100%" alt="Demo Result 9">

🚀 This repository provides minimal implementations of advanced image super-resolution algorithms:

- ⚡ **SRCNN** (Super-Resolution Convolutional Neural Network)
- 🚀 **FSRCNN** (Fast SRCNN)
- 🌀 **ESPCN** (Efficient Sub-Pixel Convolutional Neural Network)
- 🌟 **EDSR** (Enhanced Deep Residual Networks)
- 🌐 **IMDN** (Information Multi-Distillation Network)

---

## 🎉 Features

- 📸 **Comprehensive Algorithms**: Includes powerful single-image super-resolution models.
- 🔧 **Ease of Use**: Simplified configuration and training via YAML files.
- 📊 **Standard Benchmarks**: Supports datasets like Set5, Set14, BSD100, and Urban100.

---

## 💻 Quick Start

### 🚩 Installation

```bash
pip install -r requirements.txt
```

### 📂 Dataset Structure

The repository assumes the following dataset directory structure:

```yaml
project_root/
  data/
    DIV2K_train_HR/
    T91/
    Set5/
    Set14/
```

- **🏋️ Training**: `T91` and `DIV2K_train_HR`
- **🧪 Validation & 🚦 Testing**: `Set5`, `Set14`, `BSD100`, and `Urban100`

⚠️ *No need to prepare LR images manually; bicubic down-sampling is performed dynamically!*

---

## 🎯 Training

```bash
python train.py --config configs/srcnn_x2.yaml
```

---

## 📈 Evaluation

### Example: Testing with Set14 🗂️

```bash
python test.py \
  --ckpt output/srcnn_x2/best.pt \
  --test_dir data/Set14 \
  --model srcnn \
  --scale 2 \
  --save_images \
  --out_dir output/srcnn_x2/test \
  --json output/srcnn_x2/test/metrics.json
```

### Example: Testing with Custom Demo Data 🎨

```bash
python test.py \
  --ckpt output/srcnn_x2/best.pt \
  --test_dir demo/original \
  --model srcnn \
  --scale 2 \
  --save_images \
  --out_dir demo/srcnn_x2 \
  --json demo/srcnn_x2/metrics.json
```

---

## 📚 References 📚

👓 Relevant papers for implemented algorithms:

- 🧠 **SRCNN**: Dong, Chao, et al. "Learning a deep convolutional network for image super-resolution." *ECCV, 2014* ([Paper Link](https://arxiv.org/abs/1501.00092))
- 🌟 **FSRCNN**: Dong, Chao, et al. "Accelerating the super-resolution convolutional neural network." *ECCV, 2016* ([Paper Link](https://arxiv.org/abs/1608.00367))
- 🔍 **ESPCN**: Shi, Wenzhe, et al. "Real-time single image and video super-resolution using an efficient sub-pixel convolutional neural network." *CVPR, 2016* ([Paper Link](https://arxiv.org/abs/1609.05158))
- 🎨 **EDSR**: Lim, Bee, et al. "Enhanced deep residual networks for single image super-resolution." *CVPR Workshops, 2017* ([Paper Link](https://arxiv.org/abs/1707.02921))
- ✨ **IMDN**: Hui, Zheng, et al. "Lightweight image super-resolution with information multi-distillation network." *ACM MM, 2019* ([Paper Link](https://arxiv.org/abs/1909.11856))

---

🎉 **Happy Super-Resolution!** Please ⭐ this repository if you find it useful!
