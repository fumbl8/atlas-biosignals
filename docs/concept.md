# Concept Brief

## Project

**BioSignals: Disease Mechanism Cartographer** maps fragmented biomedical evidence into auditable disease mechanism maps.

The project asks whether Claude can help researchers organize disease literature into a structured layer of biological signals, proposed causal links, contradictions, convergence points, and next research questions without flattening uncertainty into a false single answer.

## Primary user

The primary user is a biomedical researcher, translational scientist, disease-area analyst, or research program lead trying to understand a complex disease area across many papers, pathways, biomarkers, model systems, and competing hypotheses.

## Use case

A user supplies paper text, abstracts, notes, or curated evidence batches for a disease area. BioSignals extracts candidate claims and organizes them into:

- mechanism-map nodes and edges,
- evidence cards tied to source references,
- contradiction ledgers where findings conflict,
- convergence views where independent evidence streams point toward shared failure patterns,
- next-step research questions, and
- plain-language research briefs.

For the initial demo, the target domain is ALS / neurodegeneration, with emphasis on mitochondrial dysfunction, oxidative stress, calcium dysregulation, excitotoxicity, protein aggregation, RNA-processing defects, neuroinflammation, glial involvement, and motor neuron failure.

## Why this is different from paper summarization

Paper summarization compresses individual documents. BioSignals is aimed at **cross-paper mechanism reasoning**.

Instead of asking only “what does this paper say?”, the project asks:

- What biological signal is being claimed?
- What entities are involved?
- What causal or associative relationship is proposed?
- What kind of evidence supports the claim?
- What model system or biological context does the claim depend on?
- Where does the evidence converge with other findings?
- Where does it contradict other findings?
- What remains unresolved?
- What research step would most reduce uncertainty?

The goal is not to replace expert interpretation. The goal is to create an inspectable scaffold that helps experts see the shape of a disease-mechanism landscape more quickly and auditably.

## Design principles

- **Evidence-linked:** Claims should stay connected to source references supplied by the user.
- **Uncertainty-aware:** Weak, indirect, model-specific, or conflicting evidence should be marked as such.
- **Contradiction-friendly:** Disagreement is useful signal, not a failure to hide.
- **Non-clinical:** The system is for research navigation, not diagnosis or treatment decisions.
- **Human-in-the-loop:** Domain experts should review, correct, and maintain the resulting mechanism maps.
