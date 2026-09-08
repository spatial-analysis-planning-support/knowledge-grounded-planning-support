# 03 LoRA Adapter Weights

LoRA adapter weights trained for the spatial diagnosis stage (base model: Qwen3-VL-32B-Instruct, from the Hugging Face official repository).

`adapter_model.safetensors` (256 MB) exceeds GitHub's per-file size limit and is distributed as an asset on the [Releases](../../releases) page.

| File | Description |
|:---|:---|
| `adapter_model.safetensors` | Adapter weights (distributed via [Releases](../../releases)) |
| `adapter_config.json` | Adapter config (r=8, alpha=32, dropout=0.05) |
| `args.json` | Training arguments |
| `trainer_state.json` | Trainer state |

## Loading

Load with `--adapters <this directory> --merge_lora true` in the inference command. The adapter is loaded only for the spatial diagnosis stage, not for the spatial improvement stage. Full commands are in `01_environment_and_reproduction/`.
