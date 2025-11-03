# Super-Resolution Minimal Reproduction
> (SRCNN / FSRCNN / ESPCN / EDSR / IMDN)

## 安装
```bash
pip install -r requirements.txt
```

## 数据
- 训练：T91 / DIV2K_train_HR 
- 验证&测试：Set5 / Set14 / BSD100 / Urban100
> 本项目默认 **在线 Bicubic 降采样** 生成 LR，无需提前准备 LR。

目录示例：
```
project_root/
  data/
    DIV2K_train_HR/
    T91/
    Set5/
    Set14/
```

## 训练
```bash
python train.py --config configs/srcnn_x2.yaml
```

## 评测
```bash
# Set14数据集
python test.py \
  --ckpt output/srcnn_x2/best.pt \
  --test_dir data/Set14 \
  --model srcnn \
  --scale 2 \
  --save_images \
  --out_dir output/srcnn_x2/test \
  --json output/srcnn_x2/test/metrics.json \

# 自己用做demo的数据集
python test.py \
  --ckpt output/srcnn_x2/best.pt \
  --test_dir demo/original \
  --model srcnn \
  --scale 2 \
  --save_images \
  --out_dir demo/srcnn_x2 \
  --json demo/srcnn_x2/metrics.json \
```

## 参考文献

- SRCNN: Dong, Chao, et al. "Learning a deep convolutional network for image super-resolution." *European Conference on Computer Vision (ECCV)*, 2014. [Paper Link](https://arxiv.org/abs/1501.00092)
- FSRCNN: Dong, Chao, et al. "Accelerating the super-resolution convolutional neural network." *European Conference on Computer Vision (ECCV)*, 2016. [Paper Link](https://arxiv.org/abs/1608.00367)
- ESPCN: Shi, Wenzhe, et al. "Real-time single image and video super-resolution using an efficient sub-pixel convolutional neural network." *IEEE Conference on Computer Vision and Pattern Recognition (CVPR)*, 2016. [Paper Link](https://arxiv.org/abs/1609.05158)
- EDSR: Lim, Bee, et al. "Enhanced deep residual networks for single image super-resolution." *IEEE Conference on Computer Vision and Pattern Recognition (CVPR) Workshops*, 2017. [Paper Link](https://arxiv.org/abs/1707.02921)
- IMDN: Hui, Zheng, et al. "Lightweight image super-resolution with information multi-distillation network." *ACM International Conference on Multimedia (MM)*, 2019. [Paper Link](https://arxiv.org/abs/1909.11856)
