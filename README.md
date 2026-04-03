# A Case Study on AI Scientists

> Benchmarking automated scientific discovery frameworks against a gold-standard AI-generated research baseline, evaluated via the GRAIL AI peer reviewer.

## Overview

Science is accelerating. Large language models can now autonomously generate hypotheses, write code, run experiments, and produce full research papers, but how good are they really? This repository presents a systematic benchmark evaluating four state-of-the-art automated scientific discovery frameworks against a gold-standard AI-generated research baseline.

## What is FARS?

**FARS (Frontier AI Research Submissions)** is a curated corpus of high-quality AI-generated research proposals hosted on the [Analemma AI platform](https://analemma.ai/fars/). Analemma is an AI-native research platform that generates structured, conference-quality research proposals across cutting-edge AI topics including safety, alignment, and machine learning systems.

Each FARS proposal covers:
- A clearly defined research problem and motivation
- A novel proposed methodology
- An experimental design with baselines and evaluation metrics
- Expected contributions and potential impact

FARS proposals serve as a **gold-standard benchmark** — they represent the target quality level that automated scientific discovery frameworks are evaluated against.

[Browse all FARS proposals at Analemma AI](https://analemma.ai/fars/)

## This Case Study

We take **FA0001** — a FARS proposal on *Canary-Controlled Safe-Data Interleaving for Emergent Misalignment Mitigation*, and feed it to four automated scientific discovery frameworks. Each framework autonomously generates a full research paper from the proposal alone, with no human guidance or intervention. All generated papers, along with the original FARS reference paper, are then evaluated by the GRAIL AI peer reviewer.

## Repository Structure
```
Automated-Science-Benchmark/
├── FARS/
│   ├── proposals/
│   │   └── FA0001_untitled.md
│   └── paper/
│       └── FA0001_FARS_paper.pdf
├── AI-Scientist-Results/
│   ├── Sakana-v1/
│   │   └── FA0001_Sakana_v1.pdf
│   ├── Sakana-v2/
│   │   └── FA0001_Sakana_v2.pdf
│   ├── CycleResearcher/
│   │   └── FA0001_Cycle_Researcher.pdf
│   └── Data-to-Paper/
│       └── FA0001_data_to_paper.pdf
└── AI-Reviewer-Results/
    └── GRAIL-Reviews/
        ├── FARS/
        │   └── FARS_Review_GRAIL.pdf
        ├── Sakana-v1/
        │   └── Sakana_v1_Review_GRAIL.pdf
        ├── Sakana-v2/
        │   └── Sakana_v2_Review_GRAIL.pdf
        ├── CycleResearcher/
        │   └── Cycle_Researcher_Review_GRAIL.pdf
        └── Data-to-Paper/
            └── Data_to_Paper_Review_GRAIL.pdf
```

## Automated Scientific Discovery Frameworks

We benchmark four frameworks, each representing a distinct approach to autonomous research generation:

| Framework | Paper | GitHub | Approach |
|-----------|-------|--------|----------|
| **Sakana AI Scientist v1** | [Lu et al., 2024](https://arxiv.org/abs/2408.06292) | [GitHub](https://github.com/SakanaAI/AI-Scientist) | Template-based LLM paper generation |
| **Sakana AI Scientist v2** | [Lu et al., 2025](https://arxiv.org/abs/2504.08066) | [GitHub](https://github.com/SakanaAI/AI-Scientist-v2) | Best-First Tree Search over idea space |
| **CycleResearcher** | [Weng et al., 2024](https://arxiv.org/abs/2411.00816) | [GitHub](https://github.com/zhu-minjun/Researcher) | Iterative review-revision pipeline |
| **Data-to-Paper** | [Ifargan et al., 2024](https://arxiv.org/abs/2404.17605) | [GitHub](https://github.com/Technion-Kishony-lab/data-to-paper) | Data-driven hypothesis generation |

## Evaluation

All papers are evaluated using the **GRAIL AI peer reviewer**, which provides structured reviews modelled on NeurIPS and ICML reviewer guidelines. Each paper is scored on four dimensions:

| Dimension | Scale | Description |
|-----------|-------|-------------|
| **Quality** | /4 | Technical quality and soundness of the work |
| **Clarity** | /4 | Clarity and organisation of the presentation |
| **Significance** | /4 | Significance and impact of the contribution |
| **Originality** | /4 | Novelty and originality of the ideas |
| **Overall** | /6 | Overall recommendation score |
| **Confidence** | /5 | Reviewer confidence in the assessment |

The overall GRAIL score is computed as:

$$\text{Overall}_{\text{GRAIL}} = \frac{1}{4}\left(S_{\text{qual}} + S_{\text{clar}} + S_{\text{sig}} + S_{\text{orig}}\right) \times \frac{6}{4}$$

### GRAIL AI Reviewer Scores

| Paper | Quality | Clarity | Significance | Originality | Overall | Confidence |
|-------|---------|---------|--------------|-------------|---------|------------|
| FARS FA0001 (Baseline) | 2/4 | 2/4 | 2/4 | 2/4 | 2/6 | 4/5 |
| Sakana v1 | 1/4 | 2/4 | 1/4 | 1/4 | 1/6 | 5/5 |
| Sakana v2 | 1/4 | 2/4 | 1/4 | 2/4 | 2/6 | 4/5 |
| CycleResearcher | 1/4 | 1/4 | 1/4 | 1/4 | 1/6 | 5/5 |
| Data-to-Paper | 1/4 | 2/4 | 1/4 | 1/4 | 1/6 | 5/5 |

## Key Findings

- The FARS baseline consistently outperforms all automated frameworks across all GRAIL dimensions
- Sakana v2 matches the FARS baseline on overall GRAIL score ($2/6$), driven by higher originality
- CycleResearcher scores lowest across all GRAIL dimensions
- GRAIL scores are uniformly low across all automated papers, suggesting current frameworks fall short of conference-level quality

## Citation
```bibtex
@misc{automated_science_benchmark_2025,
  title={Automated Science Benchmark: Evaluating AI Scientific Discovery Frameworks},
  year={2025},
  note={Case study on FA0001 from the FARS corpus — https://analemma.ai/fars/}
}
```

## Related Work

- Lu et al. (2024) — [The AI Scientist: Towards Fully Automated Open-Ended Scientific Discovery](https://arxiv.org/abs/2408.06292)
- Lu et al. (2025) — [The AI Scientist v2](https://arxiv.org/abs/2504.08066)
- Weng et al. (2024) — [CycleResearcher: Improving Automated Research via Automated Review](https://arxiv.org/abs/2411.00816)
- Ifargan et al. (2024) — [Autonomous LLM-Driven Research from Data to Human-Verifiable Research Papers](https://arxiv.org/abs/2404.17605)
- GRAIL — AI Peer Review Framework
