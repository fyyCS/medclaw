# MedClaw — project page

Source for **https://fyycs.github.io/medclaw/**, the project page for *MedClaw:
Heuristic Agent Harness for Long-Horizon Surgical Video Reasoning*.

MedClaw answers open-ended questions about long, untrimmed surgical videos by pairing
a text-only orchestrator (which never sees the pixels) with frozen vision–language
sub-agents, a coarse-to-fine tool suite, a retrieval-augmented surgical knowledge
base, and a reward-gated *Heuristic Skill Distillation* loop that mines reusable
look-here skills from the agent's own low-scoring traces. No model weights are ever
updated.

The paper also introduces **MedClawBench**: 1,123 de-leaked questions over long
surgical videos, 259 from expert-annotated neurosurgery recordings and 864 from the
held-out SVU-31K test split.

## Contents

```
index.html    the entire page — self-contained, no build step, no external requests
.nojekyll     tells GitHub Pages to serve the file as-is
```

Everything is inlined: subset WOFF2 fonts and the three paper figures as data URIs.
The page works offline and makes no third-party requests.

The leaderboard and benchmark-composition numbers are **not hand-typed**. They were
computed from the scored answer files in the research repository
([fyyCS/medclaw-agent](https://github.com/fyyCS/medclaw-agent), being opened shortly)
and injected at build time, so they match the paper exactly. The ablation and
judge-agreement tables are the exception and are transcribed from the paper.

## Data

The SVU lecture videos are the held-out test split of
[SVU-31K](https://huggingface.co/datasets/gkw0010/SVU-31K/tree/main):

```bash
huggingface-cli download gkw0010/SVU-31K --repo-type dataset --local-dir SVU-31K
```

The neurosurgery recordings are identifiable clinical footage and are not yet public.
They will be released through an application process; the questions and reference
answers ship with the benchmark file in the research repository.

## Citation

```bibtex
@article{fan2026medclaw,
  title   = {MedClaw: Heuristic Agent Harness for Long-Horizon
             Surgical Video Reasoning},
  author  = {Fan, Yingying and Du, Penghui and Zhu, Leyan and He, Runze
             and Wu, Zimeng and Zhang, Yuxuan and Chen, Liang
             and Xie, Jiahao and Wang, Jiangtang and Shao, Shuai
             and Yang, Anchao and Bai, Yutong and Wang, Yan},
  year    = {2026}
}
```

Fan and Du contributed equally.

---

Project page for MedClaw. Live at <https://fyycs.github.io/medclaw/>.
