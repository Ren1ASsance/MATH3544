# RetinaFace-PyTorch

RetinaFace 是一个高性能人脸检测器，支持精确定位人脸框、五个关键点并具备强大的多尺度检测能力。本项目基于 PyTorch 实现，并使用 WIDER FACE 数据集进行训练和评估。

## Feature

- 基于 RetinaFace 的高性能人脸检测器
- 支持五个关键点检测（眼睛、鼻子、嘴角）
- 支持多尺度预测
- 基于 PyTorch 实现，训练与推理可在 CPU 和 GPU 上运行
- 支持 WIDER FACE 数据集格式
- 支持可视化检测结果
- 支持训练日志记录与 EarlyStopping

## Project structure

```bash
RetinaFace-PyTorch/
├── data/                      # 数据集路径（需手动下载 WIDER FACE）
│   ├── WIDER_train/
│   ├── WIDER_val/
│   └── wider_face_split/
├── models/                    # 模型保存目录
├── logs/                      # 训练日志保存
├── nets/                      # 网络结构（RetinaFace 主干）
├── train.py                   # 训练脚本
├── eval.py                    # 评估脚本
├── detect.py                  # 推理脚本（可视化人脸检测）
├── utils/                     # 工具类（anchor 生成、图像增强、日志记录等）
└── README.md
```bash

## Dataset

本项目使用 WIDER FACE 数据集作为训练与测试数据。

下载步骤：
访问 WIDER FACE 数据集官网。

下载以下文件：

WIDER FACE Training Images (WIDER_train.zip)

WIDER FACE Validation Images (WIDER_val.zip)

WIDER FACE Annotations (wider_face_split.zip)

解压后目录结构如下：

kotlin
复制
编辑
data/
├── WIDER_train/
├── WIDER_val/
└── wider_face_split/


## Reference:

[bubbliiiing/retinaface-pytorch](https://github.com/bubbliiiing/retinaface-pytorch)

[serengil/retinaface](https://github.com/serengil/retinaface)

数据集来源：WIDER FACE
