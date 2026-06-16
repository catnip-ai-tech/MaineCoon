# 🐱 MaineCoon

### Pursuing a Real-Time Audio-Visual Social World Model

[![Project Website](https://img.shields.io/badge/🌐_Website-mainecoon.tech-2563EB)](https://mainecoon.tech/)
[![Blog](https://img.shields.io/badge/📝_Blog-mainecoon.tech/blogs-2563EB)](https://mainecoon.tech/blogs)
[![Technical Report](https://img.shields.io/badge/📄_Technical_Report-PDF-B91C1C)](./MaineCoon_Technical_Report.pdf)
[![Hugging Face](https://img.shields.io/badge/🤗_Hugging_Face-catnip--ai--tech-FFD21E)](https://huggingface.co/catnip-ai-tech/MaineCoon)
[![GitHub](https://img.shields.io/badge/💻_GitHub-catnip--ai--tech/MaineCoon-181717)](https://github.com/catnip-ai-tech/MaineCoon)

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

## Showcase

A few hand-picked MaineCoon generations, generated chunk-by-chunk under the streaming regime — audio-visual, with sound.

<table>
<tr>
<td>

https://github.com/user-attachments/assets/25e40042-4526-4012-bec7-7eb5491a33f6

</td>
<td>

https://github.com/user-attachments/assets/88123e96-006a-4899-98a8-c3eb99bc56dd

</td>
<td>

https://github.com/user-attachments/assets/c5dba75a-1bba-4cac-83c3-59515fad6a8c

</td>
<td>

https://github.com/user-attachments/assets/f1299019-e102-4218-8eff-fd50136abb29

</td>
</tr>
<tr>
<td>

https://github.com/user-attachments/assets/76ac6ba0-6218-4d01-aaa4-aece40a438b0

</td>
<td>

https://github.com/user-attachments/assets/dec6b4e0-8b75-4963-879b-db4d06c2614a

</td>
<td>

https://github.com/user-attachments/assets/eeda6e86-d488-4df9-919a-5166505c0e1b

</td>
<td>

https://github.com/user-attachments/assets/393bb951-59d5-455a-919e-f0880e8bb2e1

</td>
</tr>
</table>

> More demos and live, interactive sessions are available at **[mainecoon.tech](https://mainecoon.tech/)**.

## Benchmark — SocialVideo-Bench

**Table 2. Main quantitative results on SocialVideo-Bench.** MaineCoon achieves significantly better average scores than popular baselines. The two most comprehensive metrics — Audio-Visual Harmony (AVH) and Joint Audio-Visual Integrated Score (JAVIS) — consistently support MaineCoon's advantage over both streaming and bidirectional models.

| Type | Model | Vis↑ | Mot↑ | Aud↑ | IB-TV↑ | IB-TA↑ | IB-AV↑ | AV-Al↑ | AVH↑ | JAVIS↑ | **Average↑** |
|---|---|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|
| Bidirectional T2AV | JavisDiT++ | 4.39 | **2.22** | 4.06 | 0.134 | 0.070 | 0.151 | 0.312 | 0.136 | 0.112 | 0.711 |
| Bidirectional T2AV | Ovi | 4.44 | 1.89 | 3.76 | _0.138_ | 0.079 | 0.191 | **0.412** | 0.188 | 0.162 | 0.779 |
| Bidirectional T2AV | JoyAI-Echo | 4.61 | 1.17 | 3.47 | **0.147** | 0.088 | 0.226 | 0.319 | 0.196 | 0.173 | 0.749 |
| Bidirectional T2AV | MoVA | _4.66_ | 1.68 | 3.69 | 0.133 | 0.105 | 0.258 | _0.359_ | 0.245 | 0.216 | 0.842 |
| Bidirectional T2AV | LTX-2.3 | 4.10 | 0.99 | 4.06 | 0.132 | 0.111 | 0.311 | 0.334 | 0.287 | _0.247_ | 0.848 |
| Streaming TA2V | LiveAvatar | 4.60 | 1.46 | _4.13_ | 0.131 | 0.120 | _0.316_ | 0.326 | _0.291_ | 0.246 | 0.892 |
| Streaming TA2V | SoulX-FlashTalk | 4.65 | _1.99_ | 4.07 | 0.128 | _0.120_ | 0.307 | 0.279 | 0.283 | 0.238 | _0.895_ |
| **Streaming T2AV** | **MaineCoon (Ours)** | **4.71** | 1.62 | **4.35** | 0.127 | **0.130** | **0.318** | 0.334 | **0.308** | **0.272** | **0.934** |

<sub>**bold** = best, _italic_ = second best. Metrics — Vis: visual quality · Mot: motion · Aud: audio quality · IB-TV / IB-TA / IB-AV: ImageBind Text–Video / Text–Audio / Audio–Video alignment · AV-Al: audio–visual alignment · AVH: Audio-Visual Harmony · JAVIS: Joint Audio-Visual Integrated Score. See the technical report for the full benchmark and metric definitions.</sub>

**Table 3. Latency and model size comparison.** Sampling throughput (FPS) is measured for 480P 20-second video generation on a single H100 GPU. Despite having the largest model size, MaineCoon is up to **7× faster** than other streaming audio-visual generators — and even faster than a 1.3B streaming video model.

| Type | Model | Parameters | FPS↑ |
|---|---|:---:|:---:|
| Bidirectional T2AV | JavisDiT++ | 1.8B | 0.87 |
| Bidirectional T2AV | Ovi | 11B | 0.58 |
| Bidirectional T2AV | JoyAI-Echo | 23B | 18.0 |
| Bidirectional T2AV | MoVA | 32B | 0.26 |
| Bidirectional T2AV | LTX-2.3 | 22B | 1.40 |
| Bidirectional T2AV | LTX-2.3-Distilled | 22B | 20.7 |
| Streaming T2V | Causal-Forcing | 1.3B | 19.1 |
| Streaming T2V | Helios-Distilled | 14B | 18.2 |
| Streaming T2V | Krea | 14B | 6.1 |
| Streaming TA2V | LiveAvatar | 14B | 6.7 |
| Streaming TA2V | SoulX-FlashTalk | 14B | 6.6 |
| **Streaming T2AV** | **MaineCoon (Ours)** | 22B | **47.5** |

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

