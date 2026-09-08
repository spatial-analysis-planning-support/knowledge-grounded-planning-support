# Knowledge-Grounded Planning Support：复现材料

**[English](README.md) | 简体中文**

本仓库为论文 *Knowledge-Grounded Reasoning with Multimodal Large Models for Interpretable Planning Support: From Spatial Diagnosis to Improvement* 的配套复现材料，公开论文所述"空间诊断—空间优化"技术原型的关键内容，包括标注样本、LoRA 适配器权重、完整提示词模板、代表性推理记录以及运行环境与复现命令。

## 仓库结构

| 路径 | 内容 |
|:---|:---|
| `01_environment_and_reproduction/` | 运行环境、训练与推理命令、主要参数 |
| `02_annotated_samples/` | 标注样本（ms-swift 训练数据格式 JSON）及对应街景图像，覆盖五个诊断评级 |
| `03_lora_adapter_weights/` | 空间诊断阶段 LoRA 适配器权重及加载方式 |
| `04_prompt_templates/` | 诊断与优化阶段的完整提示词模板 |
| `05_representative_results/` | 代表性案例的完整"空间诊断—空间优化"推理记录（JSON）及对应街景图像 |

## LoRA 适配器权重

`adapter_model.safetensors`（256 MB）超出 GitHub 仓库单文件大小限制，通过 [Releases](../../releases) 页面附件发布。下载后置于 `03_lora_adapter_weights/` 目录下，与其余文件保持一致。md5 校验值：`94c469b3bd00f9747395676390334022`。

## 复现入口

运行环境配置、模型训练命令及两阶段推理命令见 `01_environment_and_reproduction/README.md`。

## 许可证

本仓库全部内容以 [Apache License 2.0](LICENSE) 发布。
