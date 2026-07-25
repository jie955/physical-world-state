# From Event Memory to Physical World State

**A Position on the Missing Variable in Robot World Models**

Zhang Jie · Independent Researcher · July 2026


📄 **[Read the full paper (PDF)](From_Event_Memory_to_Physical_World_State_Position_Paper.pdf)** — 11 pages, 54 references

📄🇨🇳 中文全译版 — 从事件记忆到物理世界状态：论机器人世界模型缺失的变量

---

## Overview

World Action Models (WAMs) compress interaction history into event memories to guide long-horizon robot manipulation. This position paper argues that the paradigm rests on a **missing architectural variable**: a persistent, revisable, physically-constrained, and counterfactually-simulable **Physical World State (PWS)**.

Analyzing the frontier of event-memory-based WAMs, we identify four systematic failure modes that arise because state is re-derived each step from an append-only memory rather than maintained as an independent variable:

| Failure Mode | Mechanism |
|---|---|
| **Sealed errors** | A mis-encoded record stays in memory forever; no "revise" operation exists |
| **Salience-driven forgetting** | Memory ranks history by visual salience; action demands state by physical causality — a systematic mismatch |
| **Repeated re-derivation** | State is re-fused from the memory pool every step; adjacent steps may disagree |
| **Error entrenchment** | A wrong action physically changes the world to match the error |

We further propose a **decoupling**: world models should model the *transition kernel* P(s′|s,a) over an independently-maintained state, not *be* the state. The current value of s belongs to a state tracker that persists, revises, and checks physical consistency; the world model scores the futures.

## Key Concepts

**Whiteboard vs. Notebook.** Memory is a notebook: append-only, recovered by flipping pages; a mis-written page remains forever. State is a whiteboard: it shows what is true *now*, and old facts are erased. Memory organizes information by "what is worth revisiting"; physical state must answer "what is true right now."

**The fourth property.** Persistence, revisability, and physical consistency are necessary but insufficient. A PWS must also support **counterfactual simulability** — rollout over candidate actions — which is what distinguishes a world model from a database.

**Convergence.** Two compression lines already exist and must merge: task-level progress (currently an orderless average) and object-level state (currently without task indexing). *Progress defined by object states; object states indexed by task goals.*

## Citation

```bibtex
@misc{zhang2026pws,
  author       = {Zhang, Jie},
  title        = {From Event Memory to Physical World State:
                  A Position on the Missing Variable in Robot World Models},
  year         = {2026},
  howpublished = {Position paper. GitHub: this repository},
  note         = {arXiv submission pending endorsement}
}
```

## Discussion

This paper grew out of a public comment-thread exchange with the authors of a frontier WAM system (anonymized in the text). Questions, critiques, and pointers to related work are welcome in **Issues** or **Discussions**.

## License

Paper: CC BY 4.0
