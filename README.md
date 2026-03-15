# 基于多示例学习的子宫内膜异位症 WSI 自动诊断系统

[![Jupyter Notebook](https://img.shields.io/badge/Jupyter-F37626.svg?&logo=Jupyter&logoColor=white)](https://jupyter.org/)
[![Python](https://img.shields.io/badge/python-3.8+-blue.svg)](https://www.python.org/)
[![License](https://img.shields.io/badge/license-MIT-green.svg)](LICENSE)

> **摘要**：本项目为**深圳技术大学智能医学工程专业**的本科毕业论文配套代码仓库。针对子宫内膜异位症（Endometriosis）病理全视野数字化切片（WSI），利用深度学习技术实现了自动化的特征提取与多示例学习（MIL）分类诊断。

---

## 📌 项目简介

本项目从临床病理诊断的实际需求出发，对巨大的 WSI 图像进行了边缘切割与 Patch 提取，并将特征保存为高效的 `.h5` 格式。所有的核心训练、推理代码以及运行日志均通过 **Jupyter Notebook** 进行可视化与留存，方便查阅具体的实验过程与代码逻辑。

---

## 📂 仓库目录结构

```text
├── 📁 data_features/     # 预处理后的图像特征数据 (含 .h5 文件及对应的坐标参数)
├── 📁 notebooks/         # 核心代码与运行日志 (Jupyter Notebook 格式)
│   ├── 01_wsi_preprocessing.ipynb  # WSI 边缘切割与 Patch 分块参数及代码
│   ├── 02_train_ABMIL.ipynb        # ABMIL 模型训练代码与输出日志
│   ├── 03_train_CLAM.ipynb         # CLAM 模型训练代码与输出日志
│   └── 04_train_CHIEF.ipynb        # CHIEF 模型训练代码与输出日志
├── 📄 README.md          # 项目说明文档
└── 📄 LICENSE            # 开源协议
