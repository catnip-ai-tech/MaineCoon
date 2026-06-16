# 🐱 MaineCoon

### Pursuing a Real-Time Audio-Visual Social World Model

[![Project Website](https://img.shields.io/badge/🌐_Website-mainecoon.tech-2563EB)](https://mainecoon.tech/)
[![Blog](https://img.shields.io/badge/📝_Blog-mainecoon.tech/blogs-2563EB)](https://mainecoon.tech/blogs)
[![Technical Report](https://img.shields.io/badge/📄_Technical_Report-PDF-B91C1C)](./MaineCoon_Technical_Report.pdf)
[![Hugging Face](https://img.shields.io/badge/🤗_Hugging_Face-catnip--ai--tech-FFD21E)](https://huggingface.co/catnip-ai-tech/MaineCoon)
[![GitHub](https://img.shields.io/badge/💻_GitHub-catnip--ai--tech/MaineCoon-181717)](https://github.com/catnip-ai-tech/MaineCoon)
[![Made by Catnip AI](https://img.shields.io/badge/Made_by-Catnip_AI-4E7C78)](https://github.com/catnip-ai-tech)

> **MaineCoon** is the first real-time audio-visual autoregressive model, a 22B-parameter generative core that streams synchronized audio and video chunk-by-chunk on a **single GPU**, with sub-second interaction and a record-breaking frame rate of **up to 47.5 FPS**. It is our first step toward **social world models** — generative systems that actively observe users, internally simulate social dynamics, and react to people in real time.

🔗 **Official website & demos:** **[https://mainecoon.tech/](https://mainecoon.tech/)**
📝 **Blog:** **[https://mainecoon.tech/blogs](https://mainecoon.tech/blogs)**
🤗 **Hugging Face:** **[catnip-ai-tech/MaineCoon](https://huggingface.co/catnip-ai-tech/MaineCoon)**
📄 **Technical report:** **[MaineCoon_Technical_Report.pdf](./MaineCoon_Technical_Report.pdf)**

---

## Overview

As an ever-growing majority of the world's video is watched on social platforms and created for interactive social purposes, video generation built for *social* worlds is important yet largely overlooked. Prior world models simulate physical environments or game-world exploration, but remain detached from human-centric social dynamics — they often omit audio, or fail to capture the high-engagement pacing, emotional resonance, and rapid conversational flow that define social media.

We define the position of **social world models** and build **MaineCoon** as a prototype generative core toward this goal: a real-time audio-visual generator optimized from the ground up for social-interactive applications. Unlike offline bidirectional video diffusion models, MaineCoon is designed around deployment-time streaming end-to-end — its data infrastructure, training framework, attention pattern, context distribution, KV-cache usage, and agentic streaming inference are all optimized for real-time social audio-visual generation.

## Highlights

- **⚡ Real-time on a single GPU.** A 22B interactive audio-visual autoregressive model capable of streaming generation and sub-second interaction, with a record-breaking frame rate of **up to 47.5 FPS** on a single H100. Generation cost drops well **below \$0.001 per second** — and keeps falling.
- **🌍 A new paradigm: social world models.** MaineCoon positions and serves as the first generative core for *social world models*, a technical foundation for next-generation AI-native social platforms.
- **🎓 Forcing-free streaming training.** A multi-stage training paradigm — **self-resampling**, **cross-modal representation alignment**, **domain-aware preference optimization**, and **reinforced online-policy distillation (ROPD)** — that enables native, efficient streaming audio-visual training at 22B scale.
- **🧠 Agentic streaming inference.** An agentic inference framework that supports **thousand-second-scale** generation while mitigating drift through agentic cache management, chunk commitment, long-context rollout, and prompt planning.
- **📊 SocialVideo-Bench.** A new benchmark focused on audio-visual social-video generation, with 9 representative metrics covering visual quality, motion, audio quality, audio-visual alignment, and social-video harmony. MaineCoon outperforms 7 representative open audio-visual models while achieving the fastest generation speed — a new state of the art for real-time social video generation.

## Technical Report

The full technical report is included in this repository:

📄 **[MaineCoon_Technical_Report.pdf](./MaineCoon_Technical_Report.pdf)**

It covers the social-video data infrastructure, the native streaming autoregressive training recipe, the agentic streaming inference framework, SocialVideo-Bench, and a position/outlook on social world models.

## Links

- **Website & live demos:** https://mainecoon.tech/
- **Blog:** https://mainecoon.tech/blogs
- **Hugging Face:** https://huggingface.co/catnip-ai-tech/MaineCoon
- **GitHub:** https://github.com/catnip-ai-tech/MaineCoon
- **Technical report (PDF):** [./MaineCoon_Technical_Report.pdf](./MaineCoon_Technical_Report.pdf)

> This repository hosts the technical report and project links only. It does **not** contain model weights or source code. For demos and the latest updates, please visit **[mainecoon.tech](https://mainecoon.tech/)**.

## Citation

If you find MaineCoon useful in your research, please consider citing:

```bibtex
@techreport{catnip2026mainecoon,
  title        = {MaineCoon: Pursuing A Real-Time Audio-Visual Social World Model},
  author       = {Catnip AI Team},
  year         = {2026},
  institution  = {Catnip AI},
  type         = {Technical Report},
  url          = {https://mainecoon.tech/}
}
```

## About

MaineCoon is developed by the **Catnip AI Team**.
Learn more at **[https://mainecoon.tech/](https://mainecoon.tech/)**.
