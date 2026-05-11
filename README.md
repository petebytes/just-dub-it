> ⚠️ **Notice:** This repo is now archived, please move to our [offical repository](https://github.com/Lightricks/LTX-2/tree/main/packages/ltx-pipelines#5b-lipdubpipeline) and checkout the latest LTX2.3 support on lipdub.

# JustDubit: Video Dubbing via Joint Audio-Visual Diffusion

[![Paper](https://img.shields.io/badge/arXiv-2601.22143-b31b1b?logo=arxiv)](https://arxiv.org/abs/2601.22143)
[![Website](https://img.shields.io/badge/Project-Page-181717?logo=google-chrome)](https://justdubit.github.io)
[![Model](https://img.shields.io/badge/HuggingFace-Model-orange?logo=huggingface)](https://huggingface.co/justdubit/justdubit)
[![Dataset](https://img.shields.io/badge/HuggingFace-Dataset-blue?logo=huggingface)](https://huggingface.co/datasets/justdubit/audiovisual_translation_dub/settings)

**SIGGRAPH 2026**

[Anthony Chen](https://atchen.com)\*†, Naomi Ken Korem\*, Gal Zeevi, Tavi Halperin, Matan Ben Yosef, Urska Jelercic, Ofir Bibi, Or Patashnik, Daniel Cohen-Or

_Tel Aviv University · Lightricks_

\* Equal contribution · † Work done during visit at Tel Aviv University and internship at Lightricks

## 📰 News
- [2026/05/11] 🔥 JustDubIt trained on LTX2.3 is released! check out our [offical repo](https://github.com/Lightricks/LTX-2/tree/main/packages/ltx-pipelines#5b-lipdubpipeline).
- [2026/05/11] 🔥 JustDubIt is accepted to SIGGRAPH 2026! See you in LA!
- [2026/02/10] 🔥 Code, checkpoints, and data released
- [2026/01/29] 🔥 Tech report released


---

## 📄 Abstract

Audio-Visual Foundation Models, which are pretrained to jointly generate sound and visual content, have recently shown an unprecedented ability to model multi-modal generation and editing, opening new opportunities for downstream tasks.

Among these tasks, video dubbing could greatly benefit from such priors, yet most existing solutions still rely on complex, task-specific pipelines that struggle in real-world settings.

In this work, we introduce a single-model approach that adapts a foundational audio-video diffusion model for video-to-video dubbing via a lightweight LoRA. The LoRA enables the model to condition on an input audio-video while jointly generating translated audio and synchronized facial motion.

To train this LoRA, we leverage the generative model itself to synthesize paired multilingual videos of the same speaker. Specifically, we generate multilingual videos with language switches within a single clip, and then inpaint the face and audio in each half to match the language of the other half.

By leveraging the rich generative prior of the audio-visual model, our approach preserves speaker identity and lip synchronization while remaining robust to complex motion and real-world dynamics. We demonstrate that our approach produces high-quality dubbed videos with improved visual fidelity, lip synchronization, and robustness compared to existing dubbing pipelines.

---

## 🎥 Results

| Input | Output |
|-------|--------|
| <video src="assets/Zootopia_source.mp4" width="320" controls> | <video src="assets/Zootopia_ours.mp4" width="320" controls> |
| <video src="assets/Hans_Landa_source.mp4" width="320" controls> | <video src="assets/Hans_Landa_ours.mp4" width="320" controls> |

See more results on our [project page](https://justdubit.github.io).

---

## 🚀 Quick Links

| Resource | Description |
|----------|-------------|
| [**Inference Pipeline**](packages/ltx-pipelines/README.md) | Run video dubbing with the JustDubit pipeline |
| [**Training Guide**](packages/ltx-trainer/README.md) | Train your own JustDubit LoRA |

---

## 📦 Repository Structure

```
just-dub-it/
├── packages/
│   ├── ltx-pipelines/     # Inference pipeline for video dubbing
│   │   └── README.md      # Pipeline usage guide
│   ├── ltx-trainer/       # Training tools for JustDubit LoRA
│   │   └── README.md      # Training guide
│   └── ltx-core/          # Core model components
└── README.md              # This file
```

---

## 🎬 Inference

See the [Pipeline README](packages/ltx-pipelines/README.md) for:
- Installation instructions
- Model checkpoint downloads
- Prompt format guide
- CLI arguments reference

---

## 🏋️ Training

See the [Trainer README](packages/ltx-trainer/README.md) for:
- Dataset download and preparation
- Preprocessing pipeline
- Training configuration
- Multi-GPU training setup

---

## 📝 Citation

If you find this work useful, please cite our paper:

```bibtex
@misc{chen2026justdubitvideodubbingjoint,
      title={JUST-DUB-IT: Video Dubbing via Joint Audio-Visual Diffusion}, 
      author={Anthony Chen and Naomi Ken Korem and Gal Zeevi and Tavi Halperin and Matan Ben Yosef and Urska Jelercic and Ofir Bibi and Or Patashnik and Daniel Cohen-Or},
      year={2026},
      eprint={2601.22143},
      archivePrefix={arXiv},
      primaryClass={cs.GR},
      url={https://arxiv.org/abs/2601.22143}, 
}
```


