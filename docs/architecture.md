# Architecture

BioSignals is currently a simple concept architecture for a hackathon prototype. The goal is to keep the pipeline understandable, auditable, and easy to inspect.

## High-level flow

```text
Curated papers / abstracts / notes
        ↓
Claude extraction prompts
        ↓
Evidence cards
        ↓
Mechanism map nodes + edges
        ↓
Contradiction ledger
        ↓
Convergence view
        ↓
Research next steps
        ↓
Plain-language research brief
```

## Components

### 1. User-supplied source set

The user supplies biomedical paper text, abstracts, curated snippets, or research notes with source identifiers. Early prototypes should prefer user-supplied text over automated scraping so the source set remains controlled and auditable.

### 2. Claude extraction

Claude is prompted to identify biological entities, mechanisms, claimed relationships, evidence type, evidence strength, caveats, contradictions, convergence tags, and open questions.

Prompt templates are stored in [`../prompts`](../prompts):

- [`signal_extraction_prompt.md`](../prompts/signal_extraction_prompt.md)
- [`contradiction_ledger_prompt.md`](../prompts/contradiction_ledger_prompt.md)
- [`convergence_view_prompt.md`](../prompts/convergence_view_prompt.md)

### 3. Structured JSON

Extraction results are normalized into draft JSON structures:

- [`evidence_card.schema.json`](../schemas/evidence_card.schema.json)
- [`mechanism_map.schema.json`](../schemas/mechanism_map.schema.json)
- [`contradiction_ledger.schema.json`](../schemas/contradiction_ledger.schema.json)
- [`convergence_view.schema.json`](../schemas/convergence_view.schema.json)

The schemas are intentionally simple at this stage. They are meant to support iteration, not to define a final biomedical ontology.

### 4. Evidence cards

Evidence cards preserve claim-level context. Each card should include the claim, biological entities, relationship type, evidence type, evidence strength, caveats, contradictions, source references, and next research questions.

### 5. Mechanism map

The mechanism map represents biological entities and failure processes as nodes, with proposed causal, associative, regulatory, or contextual relationships as edges.

Example node types may include:

- gene,
- protein,
- pathway,
- cellular process,
- molecular process,
- tissue process,
- disease process,
- cell type,
- biomarker,
- phenotype,
- model system,
- intervention target.

### 6. Contradiction ledger

The contradiction ledger records cases where findings disagree or appear context-dependent. This is especially important in complex disease research, where model system, species, disease stage, cell type, tissue region, assay method, and patient subtype can change interpretation.

### 7. Convergence view

The convergence view summarizes where independent evidence streams appear to point toward shared disease failure patterns. For ALS / neurodegeneration, an illustrative convergence area might connect mitochondrial stress, oxidative burden, calcium handling, glial inflammation, and motor neuron vulnerability.

Convergence should not be presented as consensus unless the supplied evidence supports that claim.

### 8. Research next steps

The next-step generator proposes follow-up literature checks, experimental questions, or validation paths that would reduce uncertainty in the map. These are research-navigation suggestions, not clinical recommendations.

### 9. Plain-language brief

A non-clinical translation layer explains the mechanism-map findings in clear language for research communication and interdisciplinary collaboration.

## Current implementation status

This repository is a public WIP concept scaffold. The next implementation step would be a small local prototype that accepts supplied abstracts, runs the prompt templates, validates JSON outputs against the schemas, and renders a simple mechanism-map view.
