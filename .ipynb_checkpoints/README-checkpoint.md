# Gemma-3 4B VQA LoRA Fine-Tuning on AMD Strix-Halo

This repository contains the code, Jupyter notebook, and pre-trained weights for fine-tuning a Google Gemma-3 4B model using Low-Rank Adaptation (LoRA) on the MIMIC-CXR Visual Question Answering (VQA) dataset. 

This project is specifically optimized for AMD's Strix-Halo APU architecture running on Linux.



## Hardware & Environment

This workflow was developed and tested on the following system configuration:
* **CPU/NPU:** AMD Ryzen AI Max+ 395
* **RAM:** 96GB Unified Memory
* **OS:** Fedora 43
* **Containerization:** Podman (Toolbox)

## Repository Contents

* `gemma-lora.ipynb`: The primary Jupyter notebook containing the end-to-end pipeline for loading the dataset, configuring the base model, setting up the LoRA adapters, and executing the fine-tuning process.
* `output-gemma-3-4b-it-lora/`: A directory containing an example of what the output will look like. (It is a really bad lora though)

## Prerequisites & Setup

Because this project relies on AMD hardware, it utilizes a specific Podman toolbox environment equipped with the necessary ROCm drivers and ML libraries.

### 1. Setup the Podman Toolbox
Before running anything in this repository, you must create and configure the AMD LLM fine-tuning environment. 

Please follow the step-by-step instructions provided in this repo by kyuz0:
👉 [kyuz0/amd-strix-halo-llm-finetuning](https://github.com/kyuz0/amd-strix-halo-llm-finetuning)

### 2. Enter the Environment
Once your toolbox is built according to the repository above, enter it using Podman:

```bash
toolbox enter <your-toolbox-name>
```

### 3. Launch the Project
Inside the toolbox environment, install any remaining Python dependencies required by the notebook (e.g., `transformers`, `peft`, `datasets`), and launch Jupyter:

```bash
jupyter notebook
```
Open `gemma-lora.ipynb` to begin exploring the code or start the fine-tuning run.
