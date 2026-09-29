# Fieldwise

An independent, interactive hackathon UI prototype inspired by [Agri-SAGE](https://arxiv.org/pdf/2607.00454).

## Run

Serve `dist/` with any static server, for example `python3 -m http.server 4173 --directory dist`, and open http://localhost:4173.

## Demo flow

1. Enter a field name, size, soil and water access.
2. Explore dry, typical or heavy-rainfall conditions.
3. Select one of three crop plans and inspect the comparison.
4. Prepare an advisory, save it on this device, or download a text copy.
5. Open Saved advisories to retrieve a draft after reloading.

## Boundaries

All yields, stress curves and scenarios are authored demonstration fixtures. Inputs apply simple illustrative adjustments, not agronomic calculations. The prototype does not execute APSIM, run an LLM, retrieve agronomy documents or fetch weather. It does not reproduce the paper's experimental results. Saved drafts use this browser's local storage and do not sync. Downloaded advisories carry the demo and review labels.

The paper studies maize in Mandya; the demo keeps district and crop fixed to that scope. Other soil selections are hypothetical extensions. A community farm advisor is the assumed user. Hackathon-specific criteria could not be verified from its client-rendered event page.

## Backend integration points

Replace `fixtures` and `current()` with a service returning candidate plans, provenance, simulation job status, verified metrics and uncertainty. Replace `runScenario()`'s demo delay with the job request and result lifecycle. Preserve the explicit distinction between model outputs, verified simulation outputs, and agronomist approval. Add consent and access control before shared farmer records.

The optional feature-detected WebMCP tool selects a displayed plan. It has no external side effects.
