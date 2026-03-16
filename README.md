# 基于多示例学习的子宫内膜异位症 WSI 自动诊断系统

[![Jupyter Notebook](https://img.shields.io/badge/Jupyter-F37626.svg?&logo=Jupyter&logoColor=white)](https://jupyter.org/)
[![Python](https://img.shields.io/badge/python-3.8+-blue.svg)](https://www.python.org/)
[![License](https://img.shields.io/badge/license-MIT-green.svg)](LICENSE)

> **摘要**：本项目为本人的本科毕业论文配套代码仓库。针对子宫内膜异位症（Endometriosis）病理全视野数字化切片（WSI），利用深度学习技术实现了自动化的特征提取与多示例学习（MIL）分类诊断。

---

## 📌 项目简介

本项目从临床病理诊断的实际需求出发，构建了完整的 WSI 处理与诊断分析流水线：
* **数据预处理**：利用 QuPath 处理不同扫描仪生成的 WSI 文件，并针对硬件限制动态调整了采样因子。采用图像识别算法进行精确的边缘分割与 Patch 提取，随后将提取出的图像区块转化为深度特征，并保存为高效的 `.pt` 和 `.h5` 格式文件。
* **模型训练与对比**：引入了 ABMIL、CLAM 与 CHIEF 等多种先进的深度学习架构进行模型训练与评估。通过十折交叉验证，系统性地对比了各模型在子宫内膜异位症识别任务中的性能表现。
* **性能优化**：为进一步突破性能瓶颈，本项目采用退火策略对 CHIEF 模型进行了精细化微调，探索并确定了适用于当前数据集的最优学习率。

 分割效果和patch切割效果展示：
 



---

## 🗂️ 关于数据集

本项目所用数据集由个人独立收集并构建，原始 WSI 数据主要来源于 [Bridge of Knowledge](https://mostwiedzy.pl/en/open-research-data/catalog) 平台的开放研究数据集。

* **数据示例**：[Endometriosis of uterus - Female, 60 - Tissue image [5280730021719611] (2022). [Data set]. Gdańsk University of Technology.](https://doi.org/10.34808/k0qe-0h08)

> **说明**：受限于开放数据协议以及 WSI 文件巨大的体积，本项目不直接开源 WSI 原始切片文件，而是提供了经过预处理和特征提取后的 `.h5` 特征文件，以便于研究者直接用于下游的模型训练与复现。

---

## ⚙️ 模型权重与环境配置

由于 ABMIL、CLAM 和 CHIEF 三个底层架构所依赖的 PyTorch 版本及第三方病理学处理库（如 OpenSlide 等）存在一定差异，为保证最佳的兼容性与运行效果，本项目**不提供统一的集成环境配置文件**。

如果您需要复现对应的运行代码，请优先参考以下各模型官方开源仓库的环境搭建指南：

* **ABMIL** (Attention-based MIL): [AMLab-Amsterdam / AttentionDeepMIL](https://github.com/AMLab-Amsterdam/AttentionDeepMIL)
* **CLAM** (Data-efficient and Weakly Supervised Computational Pathology): [mahmoodlab / CLAM](https://github.com/mahmoodlab/CLAM/tree/master)
* **CHIEF** (Clinical Histopathology Imaging Evaluation Framework): [hms-dbmi / CHIEF](https://github.com/hms-dbmi/CHIEF)

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
