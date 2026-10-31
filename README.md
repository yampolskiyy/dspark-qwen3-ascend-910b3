# DSpark-derived Qwen3-4B inference on Ascend 910B3

This repository accompanies an engineering case study of project-specific
AOT dispatch, KV-cache capacity and numerical fidelity in speculative
decoding. It does not claim a new DSpark or DFlash algorithm, universal
quality equivalence, or superiority over optimized vLLM.

## Research artifact

- [Download the versioned research archive](https://github.com/yampolskiyy/dspark-qwen3-ascend-910b3/releases/download/research-v1.1/research_artifact_v1_1.zip)
- SHA-256: `67b2eb5e297a32ecd6f6f5b4f14f79d72f38f1994577119a8126d83a4ea6a171`
- Hardware: one Ascend 910B3; Qwen3-4B; BF16; batch one.
- Scope: 21 AOT timing pairs on seven workloads, derived capture witnesses,
  and restricted V9, quality and fidelity summaries. The paper is not yet
  submitted as of this release preparation.

The archive excludes original benchmark prompts, benchmark tests and reference
answers, full model outputs, token sequences, model weights, the historical
source diff and all Multi-IF-associated per-task records. The paper reports
results for the full 100-task evaluation, including Multi-IF and an observed
regression; the restricted archive cannot independently recalculate those
full-cohort claims. Original V9 process timing receipts and raw fidelity tensors
are not included. Numerical fidelity with the source reference was not established.

The observed AOT request-latency reductions (31.24%, 21.19%, 17.01%) apply
to the stated workloads and combined intervention. Capture witnesses identify
the path at graph capture, not every operator in every replay. The external
vLLM observation is not a fair engine comparison. See the archive's README,
EVIDENCE_COVERAGE.md and RIGHTS_AND_RELEASE_DECISIONS.md for the full scope.

## Attribution and licenses

Author: Ivan Yampolskiy, Independent researcher. Original support scripts are
licensed under Apache-2.0 as scoped inside the archive. Third-party rights
and dataset terms remain separate. The source
[Multi-IF dataset](https://huggingface.co/datasets/facebook/Multi-IF)
identifies CC BY-NC 2.0; that label alone is not a blanket prohibition on
reporting aggregate results. No source dataset content is distributed here.

Related methods: [DSpark](https://arxiv.org/abs/2607.05147) and
[DFlash](https://proceedings.mlr.press/v306/chen26bv.html).
