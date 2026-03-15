# AI-based-Diagnosis-of-Endometriosis-on-Whole-Slide-Images-WSI-
基于深度学习的子宫内膜异位症 WSI 病理图像诊断系统
本项目是我的本科毕业论文课题成果。针对子宫内膜异位症（Endometriosis）病理全视野数字化切片（WSI），实现了从图像预处理、特征提取到多示例学习（MIL）分类诊断的全流程 pipeline。
仓库内容说明
本项目包含从原始图像处理到模型推理的完整组件：
数据处理 (Pre-processing)：包含 WSI 图像边缘切割参数设定及自动分块脚本。
特征数据 (Data Patches)：已处理好的 .h5 格式特征文件，可直接用于模型训练。
模型实现 (Models)：集成了三种主流的多示例学习模型：ABMIL、CLAM 以及 CHIEF。
训练日志 (Training Logs)：提供完整的训练过程记录，包括 Loss 曲线、准确率及各评价指标的变化过程。
