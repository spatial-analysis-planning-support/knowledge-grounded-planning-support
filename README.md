# Knowledge-Grounded Planning Support: Reproduction Materials

**English | [简体中文](README_CN.md)**

Reproduction materials accompanying the paper *Knowledge-Grounded Reasoning with Multimodal Large Models for Interpretable Planning Support: From Spatial Diagnosis to Improvement*. The repository provides the annotated samples, LoRA adapter weights, full prompt templates, representative inference records, and the runtime environment and commands needed to reproduce the "spatial diagnosis – spatial improvement" pipeline described in the paper.

## Repository Structure

| Path | Contents |
|:---|:---|
| `01_environment_and_reproduction/` | Runtime environment, training and inference commands, key parameters |
| `02_annotated_samples/` | Annotated samples in ms-swift training format (JSON) with street-view images, covering the five diagnosis rating levels |
| `03_lora_adapter_weights/` | LoRA adapter weights for the spatial diagnosis stage and loading instructions |
| `04_prompt_templates/` | Full prompt templates for the diagnosis and improvement stages |
| `05_representative_results/` | Complete "diagnosis – improvement" inference records (JSON) of representative cases with street-view images |

## LoRA Adapter Weights

`adapter_model.safetensors` (256 MB) exceeds GitHub's per-file size limit and is distributed as a release asset. Download it from the [Releases](../../releases) page and place it under `03_lora_adapter_weights/` together with the other files. md5: `94c469b3bd00f9747395676390334022`.

## Reproduction

See `01_environment_and_reproduction/README.md` for the environment setup, training command, and inference commands for both stages.

## License

All materials in this repository are released under the [Apache License 2.0](LICENSE).
