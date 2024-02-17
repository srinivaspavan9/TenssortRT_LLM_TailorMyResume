# Resume Tailoring Chatbot: LLM with NVIDIA TensorRT Optimization

## Introduction

Welcome to the GitHub repository for a cutting-edge chatbot that specializes in tailoring resumes to job descriptions. This chatbot is powered by a fine-tuned Large Language Model (LLM) capable of providing precise Applicant Tracking System (ATS) scores, guiding users in optimizing their resumes for various job applications. A highlight of this project is the enhanced performance through NVIDIA TensorRT optimization on RTX PCs.

## Model Architecture and Fine-Tuning

This model is built upon `mistralai/Mistral-7B-Instruct-v0.2`, using `BitsAndBytesConfig` for efficient 4-bit quantization, optimized for NVIDIA's advanced hardware. The model undergoes further refinement with `AutoPeftModelForCausalLM` configured via `LoraConfig` to prepare for `kbit` training. The fine-tuning leverages the `SFTTrainer` class from the `trl` library, with a max sequence length of 2048 tokens.

## Training Process

`TrainingArguments` set the stage for training, specifying epochs, batch size, learning rate, and evaluation strategy. We used a custom dataset using that has accurate ats scores for resumes based on the given job descriptions. The training process follows these defined parameters, ensuring the model's adeptness at generating ATS scores.

## How to Use

Post-training, the model is a bona fide expert at evaluating and enhancing resumes. It is available on Hugging Face at: [mistral_ATSscore_generation](https://huggingface.co/SlyGoblin/mistral_ATSscore_generation).

This model stands out by providing ATS scores with unparalleled accuracy.

## Performance Insights

Included in this repository are benchmarks demonstrating the inference time improvements using NVIDIA TensorRT optimization compared to standard configurations.

- ![Average Inference Time Comparison with Specified Averages](inference_comparision.png)
- ![TensorRT LLM Model Inference Time](with_tensorrt.png)
- ![Fine-tuned LLM Model Inference Time Without TensorRT](without_tesnsorrt.png)



