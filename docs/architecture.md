# Architecture

BioSignals is currently a simple concept architecture for a hackathon prototype. The goal is to keep the pipeline understandable, auditable, and easy to inspect.

## High-level flow

```text
Input papers / abstracts
        ↓
Claude extraction prompts
        ↓
Structured JSON
        ↓
Mechanism map
        ↓
Evidence cards
        ↓
Contradiction ledger
        ↓
Convergence summary
        ↓
Research next steps
        ↓
Plain-language brief
```

## Components

### 1. Input papers / abstracts

The user supplies biomedical paper text, abstracts, curated snippets, or research notes. Early prototypes should prefer user-supplied text over automated scraping so the source set remains controlled and auditable.

### 2. Claude extraction

Claude is prompted to identify biological entities, mechanisms, claimed relationships, evidence type, confidence, caveats, contradictions, convergence tags, and open questions.

Prompt templates are stored in [`../prompts`](../prompts):

- `signal_extraction_prompt.md`
- `contradiction_ledger_prompt.md`
- `convergence_view_prompt.md`

### 3. Structured JSON

Extraction results are normalized into draft JSON structures:

- [`mechanism_map.schema.json`](../schemas/mechanism_map.schema.json)
- [`evidence_card.schema.json`](../schemas/evidence_card.schema.json)

The schemas are intentionally simple at this stage. They are meant to support iteration, not to define a final biomedical ontology.

### 4. Mechanism map

The mechanism map represents biological entities and failure processes as nodes, with proposed causal, associative, regulatory, or contextual relationships as edges.

Example node types may include:

- gene/protein,
- pathway,
- cellular process,
- cell type,
- biomarker,
- disease phenotype,
- model system,
- intervention target.

### 5. Evidence cards

Evidence cards preserve claim-level context. Each card should include the claim, entities, relationship type, evidence type, confidence, caveats, contradictions, source references, and next questions.

### 6. Contradiction ledger

The contradiction ledger records cases where findings disagree or appear context-dependent. This is especially important in complex disease research, where model system, disease stage, cell type, tissue, assay, and patient subtype can change interpretation.

### 7. Convergence summary

The convergence view summarizes where independent evidence streams appear to point toward shared disease failure patterns. For ALS / neurodegeneration, an example convergence area might connect mitochondrial stress, oxidative injury, calcium handling, glial inflammation, and motor neuron vulnerability.

### 8. Research next steps

The next-step generator proposes follow-up literature checks, experimental questions, or validation paths that would reduce uncertainty in the map.

### 9. Plain-language brief

A non-clinical translation layer explains the mechanism-map findings in clear language for research communication, grant framing, patient-advocacy education, or interdisciplinary collaboration.

## Current implementation status

This repository is a public WIP concept scaffold. The next implementation step would be a small local prototype that accepts supplied abstracts, runs the prompt templates, validates JSON outputs against the schemas, and renders a simple mechanism-map view.
