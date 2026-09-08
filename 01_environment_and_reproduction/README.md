# 01 Environment and Reproduction

## Runtime Environment

- ms-swift 3.10.0.dev0 ｜ vLLM 0.11.0 ｜ PyTorch 2.8.0+cu128 ｜ CUDA 12.8
- GPU: 2 × NVIDIA RTX PRO 6000
- Base model: Qwen3-VL-32B-Instruct (from Hugging Face / ModelScope official repositories)

## Model Training

```bash
CUDA_VISIBLE_DEVICES=0,1 swift sft \
   --model autodl-tmp/qwen3_vl_32b \
   --model_type qwen3_vl \
   --train_type lora \
   --dataset autodl-tmp/1013safety_pic200/1214_训练集_train_images_train.json \
   --split_dataset_ratio 0.2 \
   --num_train_epochs 3 \
   --learning_rate 1e-4 \
   --gradient_accumulation_steps 1 \
   --eval_steps 50 \
   --save_steps 50 \
   --seed 42 \
   --bf16 true \
   --gradient_checkpointing true \
   --output_dir autodl-tmp/qwen3_vl_32b
```

LoRA is applied to all linear layers with rank=8, alpha=32, dropout=0.05. Full training arguments are recorded in `03_lora_adapter_weights/args.json`.

## Spatial Diagnosis Inference

```bash
CUDA_VISIBLE_DEVICES=0,1 \
swift infer \
    --adapters autodl-tmp/qwen3_vl_32b/安全性诊断-checkpoint/checkpoint-300 \
    --infer_backend vllm \
    --vllm_tensor_parallel_size 2 \
    --merge_lora true \
    --vllm_gpu_memory_utilization 0.9 \
    --temperature 0.7 \
    --val_dataset autodl-tmp/0115safety_neihuan_all_test.json \
    --max_model_len 4096
```

`--adapters` points to the trained LoRA weights directory, corresponding to `03_lora_adapter_weights/` in this repository; `--val_dataset` points to the inference dataset assembled in ms-swift message format.

## Spatial Improvement Inference

```bash
CUDA_VISIBLE_DEVICES=0,1 swift infer \
--model autodl-tmp/qwen3_vl_32b \
--model_type qwen3_vl \
--val_dataset autodl-tmp/20260309overall_measures_test.json \
--infer_backend vllm \
--temperature 0.7 \
--vllm_tensor_parallel_size 2 \
--stream False
```

## Key Inference Parameters

temperature = 0.7, top_p = 0.8, top_k = 20, max_model_len = 4096, seed = 42

Inputs are assembled in ms-swift message format: the system turn contains the full prompt text (see `04_prompt_templates/`), and the user-turn format is shown in the `messages` of each case under `05_representative_results/`.
