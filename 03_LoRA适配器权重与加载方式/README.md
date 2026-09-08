# 03 LoRA 适配器权重与加载方式

空间诊断阶段训练所得的 LoRA 适配器权重（基座模型 Qwen3-VL-32B-Instruct，Hugging Face 官方仓库获取）。

`adapter_model.safetensors`（256 MB）超出 GitHub 仓库单文件大小限制，通过本仓库 Releases 页面的附件发布；下载后放入本目录，与其余三个文件保持一致。

| 文件 | 说明 | md5 校验值 |
|:---|:---|:---|
| `adapter_model.safetensors` | 适配器权重 | `94c469b3bd00f9747395676390334022` |
| `adapter_config.json` | 适配器配置（r=8，alpha=32，dropout=0.05） | `d36d6cd1f34508e1588341c8b34d76a6` |
| `args.json` | 训练参数记录 | `6a93ca3ebea3445c0f92e55a34dd2182` |
| `trainer_state.json` | 训练状态记录 | `ed23e96797eb44360ee53f65c2ae309d` |

## 加载方式

推理命令中以 `--adapters <本权重目录> --merge_lora true` 加载，仅空间诊断阶段加载；空间优化阶段不加载。完整命令见 `01_运行环境与复现脚本/`。
