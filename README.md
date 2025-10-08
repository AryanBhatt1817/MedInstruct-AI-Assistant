# AlpaCare Medical Instruction Assistant

## Project Overview
Fine-tuned medical instruction assistant using LoRA/PEFT on TinyLlama-1.1B-Chat.

## Model Details
- **Base Model**: TinyLlama/TinyLlama-1.1B-Chat-v1.0 (<7B parameters)
- **License**: Apache 2.0 (permissive)
- **Dataset**: lavita/AlpaCare-MedInstruct-52k (1,500 samples used)
- **Method**: LoRA (rank=8, alpha=16) with FP32 training
- **Training Time**: ~25-30 minutes on Google Colab T4 GPU

## Safety Features
✅ Medical disclaimer added to ALL outputs
✅ Filtered diagnostic/prescription content from training
✅ Educational responses only - no clinical decisions
✅ 30 sample outputs for human evaluation

## Files Included
1. `lora_adapters.zip` - Trained LoRA adapter weights
2. `evaluation_samples.csv` - 30 samples for human review
3. This README

## How to Use
1. Load base model: TinyLlama/TinyLlama-1.1B-Chat-v1.0
2. Apply LoRA adapters from `lora_adapters.zip`
3. Format prompts as: "### Instruction:\n{query}\n\n### Response:\n"
4. All outputs include medical disclaimers

## Safety Constraints Met
- ❌ No diagnosis provided
- ❌ No prescription/dosage recommendations
- ❌ No unsupervised clinical decision rules
- ✅ Clear medical disclaimers on all outputs
- ✅ Educational information only

## Human Evaluation
- 30 medically-literate human reviews required
- evaluation_samples.csv ready for review
- Reviewers should assess: accuracy, safety, disclaimer presence

## Training Configuration
- Subset size: 1,500 samples
- Batch size: 4
- Gradient accumulation: 4
- Learning rate: 2e-4
- Epochs: 1
- LoRA rank: 8
- LoRA alpha: 16

## Disclaimer
⚠️ This model provides EDUCATIONAL information only.
⚠️ Always consult qualified healthcare professionals for medical advice.
⚠️ NOT for diagnosis, prescription, or clinical decision-making.
