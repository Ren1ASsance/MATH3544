# RetinaFace-PyTorch

RetinaFace 是一个高性能人脸检测器，支持精确定位人脸框、五个关键点并具备强大的多尺度检测能力。本项目基于 PyTorch 实现，并使用 WIDER FACE 数据集进行训练和评估。

## 🔍 项目特点

- 基于 RetinaFace 的高性能人脸检测器
- 支持五个关键点检测（眼睛、鼻子、嘴角）
- 支持多尺度预测
- 基于 PyTorch 实现，训练与推理可在 CPU 和 GPU 上运行
- 支持 WIDER FACE 数据集格式
- 支持可视化检测结果
- 支持训练日志记录与 EarlyStopping

## 📁 项目结构

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
📦 环境依赖
Python >= 3.7

PyTorch >= 1.8

torchvision

numpy

opencv-python

tqdm

可通过以下命令安装依赖：

bash
复制
编辑
pip install -r requirements.txt
📚 数据集准备
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
🚀 快速开始
1. 模型训练
bash
复制
编辑
python train.py
支持使用 CUDA 进行加速训练。

自动保存最佳模型至 models/ 文件夹。

支持 EarlyStopping，防止过拟合。

2. 模型评估
bash
复制
编辑
python eval.py
在验证集上评估检测性能（可选：mAP、Recall、Precision）。

3. 单张图片推理
bash
复制
编辑
python detect.py --image_path example.jpg
支持绘制检测框与关键点。

📊 模型结构
本项目基于如下结构实现 RetinaFace：

主干网络：MobileNetV1 或 ResNet50（可选）

Feature Pyramid Network（FPN）

SSH（Single Stage Headless）模块

回归分支（边界框、关键点、分类）

📝 模型训练设置
参数	值
输入尺寸	640x640
优化器	SGD / Adam
学习率	1e-3（CosDecay）
批大小	8 / 16
验证频率	每 N epoch
停止条件	EarlyStopping

📈 训练日志与可视化
训练过程中会将日志保存在 logs/ 文件夹，支持：

损失函数曲线

精度曲线

模型保存记录（.pth）

🙋‍♂️ 致谢
本项目参考实现：

bubbliiiing/retinaface-pytorch

serengil/retinaface

数据集来源：WIDER FACE
