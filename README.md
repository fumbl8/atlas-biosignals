# BioSignals: Disease Mechanism Cartographer

**Mapping fragmented biomedical evidence into auditable disease mechanism maps.**

BioSignals is an early-stage hackathon concept for turning fragmented biomedical literature into structured, inspectable disease mechanism maps. The project explores how Claude can help researchers move from isolated paper summaries toward an auditable view of biological signals, proposed causal relationships, evidence strength, contradictions, convergence points, and unresolved research questions.

## Problem statement

Complex diseases are studied across fragmented papers, pathways, biomarkers, and model systems. Researchers often struggle to see what failure pattern the evidence is collectively pointing toward.

## Proposed solution

BioSignals uses Claude to extract biological signals, proposed causal relationships, evidence strength, contradictions, convergence points, and unresolved research questions into an inspectable mechanism map.

The intended output is not a single polished answer. It is a structured research-navigation layer that keeps claims tied to evidence, surfaces uncertainty, and makes disagreements visible.

## Initial demo domain

The initial demo domain is **ALS / neurodegeneration**, especially:

- Mitochondrial dysfunction
- Oxidative stress
- Calcium dysregulation
- Excitotoxicity
- Protein aggregation
- RNA-processing defects
- Neuroinflammation
- Glial involvement
- Motor neuron failure

## Core modules

| Module | Purpose |
| --- | --- |
| **Signal Map** | Organizes biological entities, mechanisms, and proposed causal links into a navigable map. |
| **Evidence Cards** | Captures individual claims with evidence type, confidence, caveats, contradictions, and source references. |
| **Convergence View** | Summarizes where independent evidence streams appear to point toward shared failure patterns. |
| **Contradiction Ledger** | Tracks conflicting findings, context differences, and unresolved explanations. |
| **Research Next-Step Generator** | Proposes follow-up questions, experiments, or literature checks based on gaps and uncertainty. |
| **Plain-Language Translation** | Converts technical mechanism-map findings into non-clinical explanations for broader research communication. |

## Repository status

**Early WIP / hackathon concept.**

This repository currently contains the public-facing concept, proposed architecture, illustrative sample output, draft JSON schemas, and Claude prompt templates. It does **not** claim to be a finished tool, validated biomedical knowledge base, clinical product, or deployed system.

## Non-clinical disclaimer

BioSignals is a research-navigation and mechanism-mapping prototype, not a diagnostic or clinical decision tool. It should not be used to diagnose, treat, prevent, or make medical decisions for any disease or individual patient.

## Future direction

The long-term direction is a shared, maintained mechanism-map layer for complex disease research: a place where biomedical evidence can be continuously organized, questioned, updated, and inspected across papers, models, mechanisms, and hypotheses.

## Repository contents

```text
README.md
docs/concept.md
docs/architecture.md
docs/sample-output.md
schemas/mechanism_map.schema.json
schemas/evidence_card.schema.json
prompts/signal_extraction_prompt.md
prompts/contradiction_ledger_prompt.md
prompts/convergence_view_prompt.md
```

## License

This project is released under the MIT License. See [`LICENSE`](LICENSE).
