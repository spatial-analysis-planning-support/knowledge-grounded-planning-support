# 01 运行环境与复现脚本

## 运行环境

- ms-swift 3.10.0.dev0 ｜ vLLM 0.11.0 ｜ PyTorch 2.8.0+cu128 ｜ CUDA 12.8
- GPU：2 × NVIDIA RTX PRO 6000
- 基座模型：Qwen3-VL-32B-Instruct（Hugging Face / ModelScope 官方仓库获取）

## 模型训练

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

LoRA 作用于全部线性层，rank=8、alpha=32、dropout=0.05。完整训练参数记录见 `03_LoRA适配器权重与加载方式/args.json`。

## 空间诊断推理

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

`--adapters` 指向训练所得 LoRA 权重目录，对应本仓库 `03_LoRA适配器权重与加载方式/`；`--val_dataset` 指向待推理数据集，按 ms-swift 消息格式拼装。

## 空间优化推理

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

## 主要推理参数

temperature = 0.7，top_p = 0.8，top_k = 20，max_model_len = 4096，seed = 42

输入按 ms-swift 消息格式拼装：system 轮为提示词全文（见 `04_完整提示词模板/`），user 轮格式见 `05_代表性推理结果/` 各案例的 messages。
