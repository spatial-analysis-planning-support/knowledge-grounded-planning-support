# Knowledge-Grounded Planning Support: Reproduction Materials

Reproduction materials accompanying the paper *Knowledge-Grounded Reasoning with Multimodal Large Models for Interpretable Planning Support: From Spatial Diagnosis to Improvement*. The repository provides the annotated samples, LoRA adapter weights, full prompt templates, representative inference records, and the runtime environment and commands needed to reproduce the "spatial diagnosis – spatial improvement" pipeline described in the paper.

本仓库为论文《Knowledge-Grounded Reasoning with Multimodal Large Models for Interpretable Planning Support: From Spatial Diagnosis to Improvement》的配套复现材料，公开论文所述"空间诊断—空间优化"技术原型的关键内容，包括标注样本、LoRA 适配器权重、完整提示词模板、代表性推理记录以及运行环境与复现命令。

## Repository Structure | 仓库结构

| Path 路径 | Contents 内容 |
|:---|:---|
| `01_environment_and_reproduction/` | Runtime environment, training and inference commands, key parameters 运行环境、训练与推理命令、主要参数 |
| `02_annotated_samples/` | Annotated samples in ms-swift training format (JSON) with street-view images, covering the five diagnosis rating levels 标注样本（ms-swift 训练数据格式 JSON）及对应街景图像，覆盖五个诊断评级 |
| `03_lora_adapter_weights/` | LoRA adapter weights for the spatial diagnosis stage and loading instructions 空间诊断阶段 LoRA 适配器权重及加载方式 |
| `04_prompt_templates/` | Full prompt templates for the diagnosis and improvement stages 诊断与优化阶段的完整提示词模板 |
| `05_representative_results/` | Complete "diagnosis – improvement" inference records (JSON) of representative cases with street-view images 代表性案例的完整"空间诊断—空间优化"推理记录（JSON）及对应街景图像 |

## LoRA Adapter Weights | 权重获取

`adapter_model.safetensors` (256 MB) exceeds GitHub's per-file size limit and is distributed as a release asset. Download it from the [Releases](../../releases) page and place it under `03_lora_adapter_weights/` together with the other files. md5: `94c469b3bd00f9747395676390334022`.

`adapter_model.safetensors`（256 MB）超出 GitHub 仓库单文件大小限制，通过 [Releases](../../releases) 页面附件发布。下载后置于 `03_lora_adapter_weights/` 目录下，md5 校验值：`94c469b3bd00f9747395676390334022`。

## Reproduction | 复现入口

See `01_environment_and_reproduction/README.md` for the environment setup, training command, and inference commands for both stages.

运行环境配置、模型训练命令及两阶段推理命令见 `01_environment_and_reproduction/README.md`。

## License | 许可证

All materials in this repository are released under the [Apache License 2.0](LICENSE).

本仓库全部内容以 [Apache License 2.0](LICENSE) 发布。
