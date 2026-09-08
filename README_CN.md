# Knowledge-Grounded Planning Support：复现材料

<p align="center">
  <a href="README.md"><img alt="English" src="https://img.shields.io/badge/lang-English-blue.svg"></a>
  <a href="README_CN.md"><img alt="简体中文" src="https://img.shields.io/badge/lang-%E7%AE%80%E4%BD%93%E4%B8%AD%E6%96%87-red.svg"></a>
  <a href="LICENSE"><img alt="License" src="https://img.shields.io/badge/license-Apache%202.0-green.svg"></a>
</p>

## 关于本项目

本仓库公开研究 *Knowledge-Grounded Reasoning with Multimodal Large Models for Interpretable Planning Support: From Spatial Diagnosis to Improvement* 的复现材料。该研究提出了一种基于领域知识、面向正确且可解释的规划支持的多模态大模型方法：通过融入领域知识并引导"诊断—优化"推理，构建并验证了基于多模态大模型的规划支持技术原型，并以街道层面步行安全性提升为代表性任务，在空间诊断与空间优化两个阶段进行了评估。

为支持该技术原型的可复现性，本仓库从研究中选取以下内容公开：

- **标注样本**：部分标注样本（ms-swift 训练数据格式），覆盖五个诊断评级，附对应街景图像；
- **LoRA 适配器权重**：空间诊断阶段训练所得的 LoRA 适配器（基座模型 Qwen3-VL-32B-Instruct），以 Release 附件形式发布；
- **提示词模板**：诊断与优化阶段使用的完整提示词模板，与论文附录 B、附录 C 一致；
- **代表性推理记录**：部分测试样本上完整的"空间诊断—空间优化"推理记录；
- **环境与命令**：运行环境、模型训练命令及两阶段推理命令。

## 仓库结构

| 路径 | 内容 |
|:---|:---|
| `01_environment_and_reproduction/` | 运行环境、训练与推理命令、主要参数 |
| `02_annotated_samples/` | 标注样本（ms-swift 训练数据格式 JSON）及对应街景图像，覆盖五个诊断评级 |
| `03_lora_adapter_weights/` | 空间诊断阶段 LoRA 适配器权重及加载方式 |
| `04_prompt_templates/` | 诊断与优化阶段的完整提示词模板 |
| `05_representative_results/` | 代表性案例的完整"空间诊断—空间优化"推理记录（JSON）及对应街景图像 |

## LoRA 适配器权重

`adapter_model.safetensors`（256 MB）超出 GitHub 仓库单文件大小限制，以 [Releases](../../releases) 页面附件形式发布。

## 复现入口

运行环境配置、模型训练命令及两阶段推理命令见 `01_environment_and_reproduction/README.md`。

## 许可证

本仓库全部内容以 [Apache License 2.0](LICENSE) 发布。
