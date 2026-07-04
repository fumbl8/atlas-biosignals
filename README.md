# BioSignals: Disease Mechanism Cartographer

**WIP Claude/life-sciences prototype for mapping biomedical evidence into auditable disease-mechanism maps.**

> **Status:** Early WIP / hackathon v0. This is a small public concept scaffold, not a deployed research platform or validated biomedical system.

BioSignals is an early prototype by a biology educator and independent AI systems builder. It explores whether Claude can help organize user-supplied biomedical literature into inspectable mechanism maps: biological signals, proposed causal relationships, evidence strength, contradictions, convergence points, and unresolved research questions.

The initial demo target is **ALS / neurodegeneration**.

## What this is

- A research-navigation prototype for organizing biomedical evidence.
- A mechanism-mapping scaffold that keeps claims tied to supplied sources.
- A way to surface convergence, contradiction, context-dependence, uncertainty, and useful next questions.
- A hackathon/WIP repository intended to communicate the concept clearly before the full application is built.

## What this is not

- Not a clinical, diagnostic, therapeutic, or medical decision-support tool.
- Not a validated biomedical knowledge base.
- Not a literature-review replacement.
- Not a finished product or deployed research system.

## Problem statement

Complex diseases are studied across fragmented papers, pathways, biomarkers, model systems, cell types, and competing hypotheses. A researcher entering a field often needs more than summaries of individual papers; they need to see how claims relate, where evidence converges, where it conflicts, and what remains uncertain.

## Proposed solution

BioSignals is intended to use Claude prompts and lightweight structured schemas to extract evidence from user-supplied papers, abstracts, or notes and organize it into a mechanism map.

The intended output is not a single polished answer. It is an auditable research-navigation layer where:

- claims remain linked to source references,
- proposed causal or associative relationships are explicit,
- evidence strength and context limits are visible,
- contradictions are preserved instead of smoothed away,
- convergence patterns are separated from speculation, and
- unresolved research questions become next-step prompts.

## Differentiator: not paper summarization

Most literature-assistant workflows compress papers into summaries. BioSignals is aimed at **cross-paper mechanism mapping**.

| Instead of only asking... | BioSignals asks... |
| --- | --- |
| “What does this paper say?” | “What biological signal or mechanism is being claimed?” |
| “Can you summarize this abstract?” | “Which claims support, weaken, or complicate a proposed mechanism-map edge?” |
| “What are the key findings?” | “Where do independent evidence streams converge?” |
| “What is the conclusion?” | “Where do findings contradict each other, and what context might explain the disagreement?” |
| “What should I read next?” | “Which unresolved question would most reduce uncertainty in the map?” |

## Initial demo domain

The first demo is scoped to **ALS / neurodegeneration**, especially mechanisms such as:

- mitochondrial dysfunction,
- oxidative stress,
- calcium dysregulation,
- excitotoxicity,
- protein aggregation,
- RNA-processing defects,
- neuroinflammation,
- glial involvement, and
- motor neuron vulnerability.

## Prototype modules

| Module | Purpose |
| --- | --- |
| **Signal Extraction** | Converts supplied biomedical text into claim-level evidence cards. |
| **Mechanism Map** | Organizes biological entities, mechanisms, and proposed relationships into a navigable map. |
| **Evidence Cards** | Preserve claim-level context: evidence type, strength, caveats, contradictions, and source references. |
| **Contradiction Ledger** | Tracks conflicting findings, context differences, and unresolved explanations. |
| **Convergence View** | Summarizes where independent evidence streams appear to point toward shared failure patterns. |
| **Research Next-Step Generator** | Proposes literature checks or experimental questions that would reduce uncertainty. |
| **Plain-Language Research Brief** | Explains map-level findings in non-clinical language for interdisciplinary research communication. |

## Repository contents

```text
README.md
LICENSE
.gitignore
docs/
  concept.md
  architecture.md
  sample-output.md
prompts/
  signal_extraction_prompt.md
  contradiction_ledger_prompt.md
  convergence_view_prompt.md
schemas/
  evidence_card.schema.json
  mechanism_map.schema.json
  contradiction_ledger.schema.json
  convergence_view.schema.json
```

## Current status

**Early WIP / hackathon v0.**

This repository currently contains the public-facing concept, draft architecture, illustrative sample output, draft JSON schemas, and Claude prompt templates. It is intentionally small. The next prototype step would be a local script or notebook that accepts a curated set of abstracts, runs the prompts, validates JSON against the schemas, and renders a simple mechanism-map view.

## Non-clinical disclaimer

BioSignals is a research-navigation and mechanism-mapping prototype. It is **not** a diagnostic, therapeutic, preventive, prognostic, or clinical decision-support tool. It should not be used to diagnose, treat, prevent, manage, or make medical decisions for any disease or individual patient. Outputs require expert review and source verification.

## License

This project is released under the MIT License. See [`LICENSE`](LICENSE).
