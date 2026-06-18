# 🐱 MaineCoon

### Pursuing a Real-Time Audio-Visual Social World Model

[![Project Website](https://img.shields.io/badge/🌐_Website-mainecoon.tech-2563EB)](https://mainecoon.tech/)
[![Blog](https://img.shields.io/badge/📝_Blog-mainecoon.tech/blogs-2563EB)](https://mainecoon.tech/blogs)
[![arXiv](https://img.shields.io/badge/📄_arXiv-2606.17800-b31b1b)](https://arxiv.org/abs/2606.17800)
[![Hugging Face](https://img.shields.io/badge/🤗_Hugging_Face-catnip--ai--tech-FFD21E)](https://huggingface.co/catnip-ai-tech/MaineCoon)

> **MaineCoon** is the first real-time audio-visual autoregressive model, a 22B-parameter generative core that streams synchronized audio and video chunk-by-chunk on a **single GPU**, with sub-second interaction and a record-breaking frame rate of **up to 47.5 FPS**. It is our first step toward **social world models** — generative systems that actively observe users, internally simulate social dynamics, and react to people in real time.

🔗 **Official website & demos:** **[https://mainecoon.tech/](https://mainecoon.tech/)**

📝 **Blog:** **[https://mainecoon.tech/blogs](https://mainecoon.tech/blogs)**

🤗 **Hugging Face:** **[catnip-ai-tech/MaineCoon](https://huggingface.co/catnip-ai-tech/MaineCoon)**

📄 **Paper (arXiv):** **[arxiv.org/abs/2606.17800](https://arxiv.org/abs/2606.17800)**

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
<td width="50%" align="center">

https://github.com/user-attachments/assets/c7b122c7-a747-492b-8b0b-73061cf3e8bc

</td>
<td width="50%" align="center">

https://github.com/user-attachments/assets/04788259-7c0e-48c2-b543-1bf6c7794b63

</td>
</tr>
<tr>
<td width="50%" align="center">

https://github.com/user-attachments/assets/758ee5b9-d812-4adf-9f06-210f5bcc19c8

</td>
<td width="50%" align="center">

https://github.com/user-attachments/assets/12363249-ce66-414d-9f5e-bbaf4aa5f6e5

</td>
</tr>
<tr>
<td width="50%" align="center">

https://github.com/user-attachments/assets/f4767442-4235-4169-8129-038966fa17af

</td>
<td width="50%" align="center">

https://github.com/user-attachments/assets/921aad54-2040-4c4f-8320-20326e40fc68

</td>
</tr>
</table>

> 🎬 **Minute-scale, long-form demos** are best viewed on our **[blog](https://mainecoon.tech/blogs)**.

## Benchmark — SocialVideo-Bench

**Table 2. Main quantitative results on SocialVideo-Bench.** 🐱 **MaineCoon (Ours)** achieves the best average score and wins most metrics, including the two most comprehensive ones — Audio-Visual Harmony (AVH) and Joint Audio-Visual Integrated Score (JAVIS) — over both streaming and bidirectional baselines.

| Type | Model | Vis↑ | Mot↑ | Aud↑ | IB-TV↑ | IB-TA↑ | IB-AV↑ | AV-Al↑ | AVH↑ | JAVIS↑ | Average↑ |
|:--|:--|:--:|:--:|:--:|:--:|:--:|:--:|:--:|:--:|:--:|:--:|
| Bidirectional T2AV | JavisDiT++ | 4.39 | **2.22** | 4.06 | 0.134 | 0.070 | 0.151 | 0.312 | 0.136 | 0.112 | 0.711 |
|  | Ovi | 4.44 | 1.89 | 3.76 | _0.138_ | 0.079 | 0.191 | **0.412** | 0.188 | 0.162 | 0.779 |
|  | JoyAI-Echo | 4.61 | 1.17 | 3.47 | **0.147** | 0.088 | 0.226 | 0.319 | 0.196 | 0.173 | 0.749 |
|  | MoVA | _4.66_ | 1.68 | 3.69 | 0.133 | 0.105 | 0.258 | _0.359_ | 0.245 | 0.216 | 0.842 |
|  | LTX-2.3 | 4.10 | 0.99 | 4.06 | 0.132 | 0.111 | 0.311 | 0.334 | 0.287 | _0.247_ | 0.848 |
| Streaming TA2V | LiveAvatar | 4.60 | 1.46 | _4.13_ | 0.131 | 0.120 | _0.316_ | 0.326 | _0.291_ | 0.246 | 0.892 |
|  | SoulX-FlashTalk | 4.65 | _1.99_ | 4.07 | 0.128 | _0.120_ | 0.307 | 0.279 | 0.283 | 0.238 | _0.895_ |
| **Streaming T2AV** | 🐱&nbsp;**MaineCoon&nbsp;(Ours)** | **4.71** | 1.62 | **4.35** | 0.127 | **0.130** | **0.318** | 0.334 | **0.308** | **0.272** | **0.934**&nbsp;🥇 |

<sub>🐱 = our method &nbsp;·&nbsp; **bold** = best, _italic_ = second best. &nbsp; Metrics — Vis: visual quality · Mot: motion · Aud: audio quality · IB-TV / IB-TA / IB-AV: ImageBind Text–Video / Text–Audio / Audio–Video alignment · AV-Al: audio–visual alignment · AVH: Audio-Visual Harmony · JAVIS: Joint Audio-Visual Integrated Score. See the technical report for the full benchmark and metric definitions.</sub>

**Table 3. Latency and model size comparison.** Sampling throughput (FPS) is measured for 480P 20-second generation on a single H100 GPU. 🐱 **MaineCoon (Ours)** has the **largest model yet by far the fastest** speed — up to **7× faster** than other streaming audio-visual generators, and faster even than a 1.3B streaming video model.

| Type | Model | Params | FPS↑ |
|:--|:--|:--:|:--:|
| Bidirectional T2AV | JavisDiT++ | 1.8B | 0.87 |
|  | Ovi | 11B | 0.58 |
|  | JoyAI-Echo | 23B | 18.0 |
|  | MoVA | 32B | 0.26 |
|  | LTX-2.3 | 22B | 1.40 |
|  | LTX-2.3-Distilled | 22B | _20.7_ |
| Streaming T2V | Causal-Forcing | 1.3B | 19.1 |
|  | Helios-Distilled | 14B | 18.2 |
|  | Krea | 14B | 6.1 |
| Streaming TA2V | LiveAvatar | 14B | 6.7 |
|  | SoulX-FlashTalk | 14B | 6.6 |
| **Streaming T2AV** | 🐱&nbsp;**MaineCoon&nbsp;(Ours)** | **22B** | **47.5**&nbsp;🥇 |

<sub>🐱 = our method &nbsp;·&nbsp; **bold** = best, _italic_ = second best. FPS for 480P-20s on a single H100.</sub>

## Paper

The full paper is available on arXiv:

📄 **[arXiv:2606.17800](https://arxiv.org/abs/2606.17800)**

It covers the social-video data infrastructure, the native streaming autoregressive training recipe, the agentic streaming inference framework, SocialVideo-Bench, and a position/outlook on social world models.

## Links

- **Website & live demos:** https://mainecoon.tech/
- **Blog:** https://mainecoon.tech/blogs
- **Hugging Face:** https://huggingface.co/catnip-ai-tech/MaineCoon
- **Paper (arXiv):** https://arxiv.org/abs/2606.17800

> This repository hosts the project README, demo showcase, and links. It does **not** contain model weights or source code. For demos and the latest updates, please visit **[mainecoon.tech](https://mainecoon.tech/)**.

## Acknowledgements

MaineCoon stands on the shoulders of the open-source community. We are especially grateful to:

- **🎬 LTX-2.3 & the LTX series — [Lightricks](https://github.com/Lightricks).** MaineCoon's audio-visual backbone builds on the excellent open **LTX-2.3** model. Huge credit to the LTX team and the broader LTX-Video series.
  - **LTX-2** (incl. LTX-2.3): https://github.com/Lightricks/LTX-2
  - **LTX-Video**: https://github.com/Lightricks/LTX-Video
- **⚡ DMD series & the distribution-matching distillation community.** Our reinforced online-policy distillation (ROPD) builds on the **Distribution Matching Distillation (DMD / DMD2)** line of work and the wider few-step / real-time distillation community.
  - **DMD2**: https://github.com/tianweiy/DMD2
  - **DMD** (project page): https://tianweiy.github.io/dmd/

We thank these projects and their communities for advancing real-time, few-step, and streaming video generation.

## Citation

If you find MaineCoon useful in your research, please consider citing:

```bibtex
@article{catnip2026mainecoon,
  title        = {MaineCoon: Pursuing A Real-Time Audio-Visual Social World Model},
  author       = {Catnip AI Team},
  year         = {2026},
  journal      = {arXiv preprint arXiv:2606.17800},
  url          = {https://arxiv.org/abs/2606.17800}
}
```

## About

MaineCoon is developed by the **Catnip AI Team**.
Learn more at **[https://mainecoon.tech/](https://mainecoon.tech/)**.

