---
base_model: google/gemma-3-4b-it
library_name: peft
model_name: output-gemma-3-4b-it-lora
tags:
- base_model:adapter:google/gemma-3-4b-it
- lora
- sft
- transformers
- trl
licence: license
pipeline_tag: text-generation
---

# Model Card for output-gemma-3-4b-it-lora

This model is a fine-tuned version of [google/gemma-3-4b-it](https://huggingface.co/google/gemma-3-4b-it).
It has been trained using [TRL](https://github.com/huggingface/trl).

## Quick start

```python
from transformers import pipeline

question = "If you had a time machine, but could only go to the past or the future once and never return, which would you choose and why?"
generator = pipeline("text-generation", model="None", device="cuda")
output = generator([{"role": "user", "content": question}], max_new_tokens=128, return_full_text=False)[0]
print(output["generated_text"])
```

## Training procedure

[<img src="https://raw.githubusercontent.com/wandb/assets/main/wandb-github-badge-28.svg" alt="Visualize in Weights & Biases" width="150" height="24"/>](https://wandb.ai/andy2639le-atos/spring_2026_research/runs/hps8ogye) 


This model was trained with SFT.

### Framework versions

- PEFT 0.18.1
- TRL: 0.27.2
- Transformers: 5.0.0
- Pytorch: 2.11.0a0+rocm7.12.0a20260203
- Datasets: 4.5.0
- Tokenizers: 0.22.2

## Citations



Cite TRL as:
    
```bibtex
@misc{vonwerra2022trl,
	title        = {{TRL: Transformer Reinforcement Learning}},
	author       = {Leandro von Werra and Younes Belkada and Lewis Tunstall and Edward Beeching and Tristan Thrush and Nathan Lambert and Shengyi Huang and Kashif Rasul and Quentin Gallou{\'e}dec},
	year         = 2020,
	journal      = {GitHub repository},
	publisher    = {GitHub},
	howpublished = {\url{https://github.com/huggingface/trl}}
}
```