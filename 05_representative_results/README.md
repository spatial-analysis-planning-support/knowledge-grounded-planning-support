# 05 Representative Results | 代表性推理结果

Complete inference records of representative cases, showing the full "spatial diagnosis – spatial improvement" pipeline. Each case includes the street-view image, the diagnosis output (with the LoRA adapter loaded), and the improvement output (base model, without the adapter).

代表性案例的完整推理记录，展示"空间诊断—空间优化"完整流程。每个案例包含街景图像、诊断输出（加载 LoRA 适配器）与优化输出（基座模型，不加载适配器）。

| Path 路径 | Contents 内容 |
|:---|:---|
| `images/` | Street-view images of the cases 案例街景图像 |
| `diagnosis_outputs/` | Diagnosis-stage outputs (JSON, model response with full reasoning) 诊断阶段输出（JSON，含完整推理过程的模型应答） |
| `strategy_outputs/` | Improvement-stage outputs (JSON) 优化阶段输出（JSON） |

The user-turn input format used in inference can be found in the `messages` field of each record.

推理所用的 user 轮输入格式见各记录的 `messages` 字段。
