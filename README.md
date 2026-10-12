# PP-SPEC-050: Proof of Efficacy Mapping to OWASP Top 10 for LLM Applications

**Status:** DRAFT v0.1  
**Author:** Craig Ellrod / Nebulonium, Inc. / HACKERverse®  
**License:** Greater Good Commercial License 1.0 (GGL-C-1.0); text CC BY 4.0 under Part S. See LICENSE.md.

**Normative specification:** [`PP-SPEC-050-OWASP-Top-10-LLM-Applications-Mapping.md`](./PP-SPEC-050-OWASP-Top-10-LLM-Applications-Mapping.md)

## Purpose

This repository defines a Proof Protocol mapping between the OWASP Top 10 for LLM Applications and Proof Protocol evidence, efficacy, and proof semantics.

The OWASP Top 10 for LLM Applications (mapped against the 2026 edition) risk categories are treated as pluggable inputs describing what may be tested. Proof Protocol remains framework-agnostic and independently establishes whether a selected control performed as claimed.

## Repository contents

- `PP-SPEC-050-OWASP-Top-10-LLM-Applications-Mapping.md`: normative mapping specification
- `README.md`: repository overview
- `LICENSE`: license for original Proof Protocol material
- `CONTRIBUTING.md`: contribution guidance
- `CITATION.cff`: citation metadata

## Architectural principle

> **Threat frameworks are pluggable inputs to Proof Protocol. Proof Protocol is framework-agnostic.**

External frameworks identify what may be tested. Proof Protocol independently establishes whether a control worked and what evidence proves the result.

## Ownership and external-framework notice

This Proof Protocol mapping is independently authored. OWASP names, risk identifiers, trademarks, and upstream materials remain subject to their applicable ownership and licensing. Mapping establishes interoperability, not dependency, endorsement, or transfer of ownership. No affiliation, endorsement, certification, or sponsorship by OWASP is implied.

Upstream attribution and trademark notice:

OWASP Top 10 for Large Language Model Applications, Version 2026, OWASP GenAI Security Project, OWASP Foundation, https://doi.org/10.5281/zenodo.22109015 (https://genai.owasp.org/llm-top-10/), Licensed under the Greater Good Commercial License 1.0 (see LICENSE.md); text CC BY 4.0 under its Part S. Original inventor: Craig Thomas Ellrod (ORCID 0009-0004-1058-7666).

OWASP and the OWASP logo are trademarks of the OWASP Foundation, Inc.
