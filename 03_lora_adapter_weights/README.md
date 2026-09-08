# 03 LoRA Adapter Weights

LoRA adapter weights trained for the spatial diagnosis stage (base model: Qwen3-VL-32B-Instruct, from the Hugging Face official repository).

`adapter_model.safetensors` (256 MB) exceeds GitHub's per-file size limit and is distributed as an asset on the [Releases](../../releases) page. Download it and place it in this directory, keeping it together with the other three files.

| File | Description | md5 |
|:---|:---|:---|
| `adapter_model.safetensors` | Adapter weights | `94c469b3bd00f9747395676390334022` |
| `adapter_config.json` | Adapter config (r=8, alpha=32, dropout=0.05) | `d36d6cd1f34508e1588341c8b34d76a6` |
| `args.json` | Training arguments | `6a93ca3ebea3445c0f92e55a34dd2182` |
| `trainer_state.json` | Trainer state | `ed23e96797eb44360ee53f65c2ae309d` |

## Loading

Load with `--adapters <this directory> --merge_lora true` in the inference command. The adapter is loaded only for the spatial diagnosis stage, not for the spatial improvement stage. Full commands are in `01_environment_and_reproduction/`.
