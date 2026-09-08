# 03 LoRA Adapter Weights | LoRA 适配器权重与加载方式

LoRA adapter weights trained for the spatial diagnosis stage (base model: Qwen3-VL-32B-Instruct, from the Hugging Face official repository).

空间诊断阶段训练所得的 LoRA 适配器权重（基座模型 Qwen3-VL-32B-Instruct，Hugging Face 官方仓库获取）。

`adapter_model.safetensors` (256 MB) exceeds GitHub's per-file size limit and is distributed as an asset on the [Releases](../../releases) page. Download it and place it in this directory, keeping it together with the other three files.

`adapter_model.safetensors`（256 MB）超出 GitHub 仓库单文件大小限制，通过 [Releases](../../releases) 页面附件发布；下载后放入本目录，与其余三个文件保持一致。

| File 文件 | Description 说明 | md5 |
|:---|:---|:---|
| `adapter_model.safetensors` | Adapter weights 适配器权重 | `94c469b3bd00f9747395676390334022` |
| `adapter_config.json` | Adapter config (r=8, alpha=32, dropout=0.05) 适配器配置 | `d36d6cd1f34508e1588341c8b34d76a6` |
| `args.json` | Training arguments 训练参数记录 | `6a93ca3ebea3445c0f92e55a34dd2182` |
| `trainer_state.json` | Trainer state 训练状态记录 | `ed23e96797eb44360ee53f65c2ae309d` |

## Loading | 加载方式

Load with `--adapters <this directory> --merge_lora true` in the inference command. The adapter is loaded only for the spatial diagnosis stage, not for the spatial improvement stage. Full commands are in `01_environment_and_reproduction/`.

推理命令中以 `--adapters <本权重目录> --merge_lora true` 加载，仅空间诊断阶段加载；空间优化阶段不加载。完整命令见 `01_environment_and_reproduction/`。
