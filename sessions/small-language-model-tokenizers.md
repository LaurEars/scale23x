# A Practical Guide to Training a Small Language Model: Tokenizers, Training, and Real-World Pitfalls

https://www.socallinuxexpo.org/scale/23x/presentations/practical-guide-training-small-language-model-tokenizers-training-and-real

- **Date**: Friday, March 6, 2026
- **Time**: 15:45 - 16:45
- **Location**: Ballroom DE
- **Speaker(s)**: David vonThenen, Senior AI/ML Engineer, NetApp

> "Small Language Models are finally practical for everyday applications: they're cheaper to run, fast enough for real-time tasks, and easy to ship." The session demonstrates an end-to-end workflow using open-source tools, encompassing corpus selection, tokenizer implementation, model architecture design, and knowledge distillation training.
>
> The presentation covers practical training techniques including fine-tuning, teacher-student model comparison, batching optimization, learning rate adjustment, and checkpointing strategies. Attendees will learn weight transfer methods and dynamic int8 quantization for CPU deployment.
>
> The speaker addresses common implementation challenges: "tokenizer mismatches, unstable learning rates, temperature choices, over-checkpointing, and memory pressure on single-GPU rigs." The session concludes with reproducible scripts and guidance for local or homelab deployment, enabling participants to train and deploy compact language models balancing accuracy with computational efficiency.

## Overview

An end-to-end walkthrough of training, fine-tuning, and deploying a small language model using open-source tools, with frank coverage of the pitfalls that derail real-world training runs on limited hardware.

## Key Points

- Features of SLMs
  - Lower parameters
  - Limited context windows
  - Smaller vector dimensions (reasoning capacity)
- Use StreamingTokenDataset
- No epochs, step based
- Example with SQL SLM model
