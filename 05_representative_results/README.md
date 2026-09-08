# 05 Representative Results

Complete inference records of representative cases, showing the full "spatial diagnosis – spatial improvement" pipeline. Each case includes the street-view image, the diagnosis output (with the LoRA adapter loaded), and the improvement output (base model, without the adapter).

| Path | Contents |
|:---|:---|
| `images/` | Street-view images of the cases |
| `diagnosis_outputs/` | Diagnosis-stage outputs (JSON, model response with full reasoning) |
| `strategy_outputs/` | Improvement-stage outputs (JSON) |

The user-turn input format used in inference can be found in the `messages` field of each record.
