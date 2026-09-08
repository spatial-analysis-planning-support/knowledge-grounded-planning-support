# Knowledge-Grounded Planning Support: Reproduction Materials

<p align="center">
  <a href="README.md"><img alt="English" src="https://img.shields.io/badge/lang-English-blue.svg"></a>
  <a href="README_CN.md"><img alt="简体中文" src="https://img.shields.io/badge/lang-%E7%AE%80%E4%BD%93%E4%B8%AD%E6%96%87-red.svg"></a>
  <a href="LICENSE"><img alt="License" src="https://img.shields.io/badge/license-Apache%202.0-green.svg"></a>
</p>

## About

This repository releases reproduction materials from the study *Knowledge-Grounded Reasoning with Multimodal Large Models for Interpretable Planning Support: From Spatial Diagnosis to Improvement*. The study proposes a knowledge-grounded approach toward correct and interpretable planning support using multimodal large models. By integrating domain knowledge and guiding diagnosis–improvement reasoning, a technological prototype based on a multimodal large model is developed and validated, taking street-level pedestrian safety improvement as a representative task across spatial diagnosis and improvement.

To support reproducibility of the prototype, this repository openly provides selected materials from the study:

- **Annotated samples**: a subset of the annotated samples in ms-swift training data format, covering the five diagnosis rating levels, with the corresponding street-view images;
- **LoRA adapter weights**: the LoRA adapter trained for the spatial diagnosis stage (base model: Qwen3-VL-32B-Instruct), released as a release asset;
- **Prompt templates**: the full prompt templates used in the diagnosis and improvement stages, consistent with Appendices B and C of the paper;
- **Representative inference records**: complete "spatial diagnosis – spatial improvement" inference records on a subset of test samples;
- **Environment and commands**: the runtime environment, model training command, and inference commands for both stages.

## Repository Structure

| Path | Contents |
|:---|:---|
| `01_environment_and_reproduction/` | Runtime environment, training and inference commands, key parameters |
| `02_annotated_samples/` | Annotated samples in ms-swift training format (JSON) with street-view images, covering the five diagnosis rating levels |
| `03_lora_adapter_weights/` | LoRA adapter weights for the spatial diagnosis stage and loading instructions |
| `04_prompt_templates/` | Full prompt templates for the diagnosis and improvement stages |
| `05_representative_results/` | Complete "diagnosis – improvement" inference records (JSON) of representative cases with street-view images |

## LoRA Adapter Weights

`adapter_model.safetensors` (256 MB) exceeds GitHub's per-file size limit and is distributed as a release asset. Download it from the [Releases](../../releases) page and place it under `03_lora_adapter_weights/`.

## Reproduction

See `01_environment_and_reproduction/README.md` for the environment setup, training command, and inference commands for both stages.

## License

All materials in this repository are released under the [Apache License 2.0](LICENSE).
