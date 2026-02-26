# clhear-data-model

CLHEAR Data Model is the open, standardised schema for encoding regulatory obligations, risks, controls, procedures, and evidence across the compliance lifecycle. It enables regulators, financial institutions, vendors, and advisors to map rules, business activities, policies, SOPs, Q&As, and legal opinions into a shared machine-readable language that any system can understand and build on.

## Goals

- Provide a public, extensible data model for compliance programmes.  
- Harmonise regulatory obligations and business activities into a common structure.  
- Enable AI-ready automation, auditability, and supervisory visibility.  
- Support an ecosystem of open and commercial tools that speak the same language.  

## What This Repository Contains

Planned structure (subject to evolution as the standard matures):

- `schema/` – Core schemas and ontologies (entities, relationships, attributes).  
- `schema/core/` – Core entity definitions (e.g. Entity, BusinessActivity, Obligation, Risk, Control, SOP).  
- `schema/extensions/` – Jurisdiction- or sector-specific extensions (e.g. FCA‑UK, SEC‑US).  
- `mappings/` – Regulatory mappings by jurisdiction, rule set, and business activity, with applicability conditions and source links.  
- `patterns/` – Reusable patterns for policies, SOPs, control libraries, testing plans, issues, and Q&As.  
- `examples/` – Example implementations for different firm types and use cases (e.g. a UK retail brokerage scenario).  
- `docs/` – Conceptual documentation, design notes, governance, and contribution guides.  

## Core Entity Types

The CLHEAR Data Model is organised around a small set of core, reusable entity types, including:

- **Entity & License** – Legal entities, regulatory permissions and regimes.  
- **BusinessActivity** – Services, instruments, client segments, and channels.  
- **Obligation** – Normalised regulatory duties with citations, applicability rules, and lifecycle metadata.  
- **Risk** – Linked to obligations and activities, with inherent/residual ratings.  
- **Control** – Policies, processes, and structural controls mapped to obligations, with metrics and evidence requirements.  
- **GovernanceRole & Committee** – Roles and forums accountable for specific obligations, risks, and controls.  
- **System & DataAsset** – Technology and data stores relied on for controls, monitoring, and reporting.  
- **SOP (Standard Operating Procedure)** – Operational workflows with triggers, steps, SLAs, roles, and evidence outputs.  
- **AssurancePlan & TestResult** – Monitoring, testing, and audit activities over obligations and controls.  
- **Issue & RemediationAction** – Findings, root cause analysis, and tracked remediation linked back to affected obligations.  

These entities live in `schema/core/`, with jurisdiction-specific extensions in `schema/extensions/`, and are demonstrated through end‑to‑end examples in `examples/`.

## Example: UK Retail Stock Brokerage

As a concrete illustration, a UK online broker (e.g. offering execution‑only stock trading to retail clients) would model:

- An **Entity** with FCA firm reference number, licences and UK MiFID permissions.  
- A **BusinessActivity** for “UK retail stock brokerage” with instruments, client segments, and channels.  
- **Obligations** for best execution, client money segregation, client reporting, conflicts, governance, and operational resilience, each with FCA / MiFID citations and applicability rules.  
- Linked **Risks** (e.g. best execution failure, client money misuse) with inherent and residual ratings.  
- **Controls** such as best execution policy, execution monitoring, designated client bank accounts, and daily CASS reconciliations, each with evidence requirements and system dependencies.  
- **GovernanceRoles & Committees** (e.g. CCO, CASS Oversight Officer, Product Governance Committee) mapped to specific obligations and decisions.  
- **Systems & DataAssets** (e.g. trade data warehouse, CASS reconciliation tool, client ledger) linked to controls and obligations.  
- **SOPs** for quarterly best execution reviews, daily CASS reconciliations, incident handling, and complaints management.  
- **AssurancePlans** and **TestResults** for thematic reviews, internal audit, and external CASS audits.  
- **Issues & RemediationActions** documenting findings (e.g. reconciliation breaks) and the remediation lifecycle.  

An end‑to‑end JSON example for such a use case will be provided under `examples/uk/`.

## Design Principles

- **Open** – Licensed for broad reuse, including commercial implementations.  
- **Extensible** – Core model plus jurisdiction- and firm-specific extensions.  
- **Traceable** – Every element can be linked back to regulatory sources and evidence.  
- **Tool‑agnostic** – Usable from any tech stack, including CLHEAR’s own platform.  
- **Lifecycle‑aware** – Built to track ownership, status, testing and remediation over time.  

## Getting Started

1. Browse `schema/core/` to understand the main entity types and relationships.  
2. Explore `schema/extensions/` and `mappings/` for jurisdiction‑specific fields and regulatory mappings.  
3. Look at `patterns/` for reusable shapes of policies, SOPs, controls, and assurance plans.  
4. Review `examples/` for complete scenarios (starting with a UK retail brokerage case).  

Initial folders and files will be added as the model is extracted and stabilised.

## Contributing

CLHEAR Data Model is intended as a community standard for compliance data. Contributions are welcome from:

- Regulators and supervisory bodies.  
- Compliance officers, risk managers, and legal teams.  
- Vendors, integrators, and open‑source developers.  

You can contribute by:

- Proposing or refining schema elements in `schema/core/` or `schema/extensions/`.  
- Adding or improving regulatory mappings in `mappings/`.  
- Contributing patterns and worked examples in `patterns/` and `examples/`.  
- Enhancing documentation and design notes in `docs/`.  

Please open an issue or pull request to discuss changes. A more detailed contribution guide and governance model will follow as the community grows.

## License

This project is licensed under the Apache License 2.0. See `LICENSE` for details.
