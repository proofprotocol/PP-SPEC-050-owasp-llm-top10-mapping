# PP-SPEC-050: Proof of Efficacy Mapping to OWASP Top 10 for LLM Applications

| Field | Value |
|---|---|
| Status | DRAFT v0.1 |
| Author | Craig Ellrod, Nebulonium, Inc. (dba HACKERverse®) |
| Date | October 8, 2026 |
| License | CC BY 4.0 |
| Maps to | OWASP Top 10 for LLM Applications (mapped against the 2026 edition) |
| Series | Proof Protocol Framework Mapping Specifications |

---

## 1. Purpose

This specification defines how risk categories from the OWASP Top 10 for Large Language Model Applications can be bound to Proof Protocol test cases, evidence, and efficacy results.

OWASP remains authoritative for its own risk definitions, identifiers, terminology, and guidance. This document defines a **Proof Protocol mapping** and does not supersede or modify the OWASP project.

## 2. Scope

The OWASP Top 10 for LLM Applications is maintained by the OWASP GenAI Security Project, an OWASP Foundation project. As of October 2026 the current edition is the 2026 edition, published in August 2026; the 2025 edition is the previous release. Entries use the identifier format LLMNN:YYYY (for example LLM01:2026), where the number is the rank within that edition. Identifiers are edition-specific: the same number can denote a different risk in a different edition.

The OWASP Top 10 for LLM Applications supplies LLM application risk context that can identify what should be exercised. Proof Protocol supplies an independent evidence model for determining what happened during a test and whether a selected defensive control performed as claimed.

Independent witnessing and evidence-capture implementation are defined elsewhere in the Proof Protocol specification family.

## 3. Core Question

Proof of efficacy asks:

> **Was there a control, and did it work?**

An OWASP risk category identifies a class of concern. A product, architecture, policy, or safeguard may claim to mitigate that concern. Proof Protocol binds the risk context, adversarial test, control, observed behavior, downstream outcome, and evidence into a result that can be independently examined.

## 4. Metric Definitions

Against a defined adversarial corpus, each case is recorded as **blocked**, **detected**, **missed**, or **INVALID**.

Relevant measurements include:

- containment rate;
- detection rate;
- miss rate;
- false-positive rate against paired benign cases;
- robustness against prompt manipulation, bypass, encoding and obfuscation, poisoning, data extraction, output manipulation, resource exhaustion, or other applicable LLM attack variants;
- version-level results; and
- INVALID status when required evidence is incomplete or broken.

Target levels are engagement- and risk-specific rather than imposed by this mapping.

## 5. Evidence Produced

Mapped tests can produce:

- **Proof records** binding OWASP risk identifier and edition, test case, control, system/version, verdict, timestamp, and evidence references;
- **ProofStamp™** trusted timestamps bound to evidence/verdict objects;
- **ProofBundle™** packages containing proof records, metrics, corpus manifests, and environment/context;
- **ProofRegister™** records for issued proof artifacts; and
- corpus and environment manifests identifying the tested LLM application conditions.

## 6. Mapping to OWASP Top 10 for LLM Applications

The exact OWASP risk identifiers and names SHOULD be taken from the authoritative edition being mapped and recorded in the ProofBundle™ with the edition year as part of the identifier (for example LLM01:2026). This specification does not redefine those categories and does not reproduce OWASP risk descriptions.

| OWASP LLM-risk context | Proof Protocol treatment | Evidence |
|---|---|---|
| Edition (for example 2026 or 2025) | Record the edition; identifiers MUST NOT be compared across editions by number alone. | Corpus/test metadata |
| Risk identifier (LLMNN:YYYY) | Bind the authoritative identifier and edition to the test case. | Proof record; corpus metadata |
| Adversarial condition | Represent the risk as one or more reproducible, independently authored test cases. | Corpus manifest |
| Paired benign condition | Exercise matched benign inputs to measure false positives. | False-positive evidence |
| Control/mitigation claim | Record the asserted prevention, detection, or response behavior separately from observed effect. | Control descriptor |
| Model input and output | Capture the input presented and the output produced at the model and application boundary. | Execution evidence |
| Detection outcome | Record whether the tested condition was identified. | Detection result |
| Prevention/containment outcome | Determine whether the adversarial objective reached the protected target, data, or downstream system. | Outcome evidence |
| Tool, plugin, or downstream action | Exercise actions inside and outside asserted authority or policy limits where the application can act. | Proof records |
| Retrieval, embedding, or context boundary | Exercise manipulation, poisoning, or unauthorized-access conditions where applicable. | Robustness evidence |
| Downstream effect | Obtain target, application, tool, SIEM, vendor, or equivalent evidence when necessary to establish efficacy. | Outcome evidence |
| System/version context | Bind material model, prompt, policy, retrieval, tool, control, and environment versions to the result. | Environment descriptor |

## 7. Interoperability Rules

1. The authoritative OWASP project, edition, and applicable risk identifier (including the edition year) SHOULD be recorded.
2. OWASP identifiers, names, and terminology MUST NOT be silently redefined.
3. Proof Protocol verdicts are Proof Protocol results; they are not OWASP scores, certifications, or endorsements.
4. A control's presence, configuration, activation, and efficacy are distinct facts.
5. A policy decision, alert, or control trigger does not by itself establish efficacy when the claim concerns a downstream protected outcome.
6. Target, application, tool, SIEM, vendor, or equivalent evidence SHOULD complete the evidence round trip when required to establish the result.
7. Missing required evidence MUST yield **INVALID**, not PASS.
8. Material changes to the tested system, model, policy, tools, permissions, control, environment, OWASP mapping, or corpus SHOULD trigger retesting where they can affect the result.
9. OWASP risk descriptions and other OWASP text SHOULD NOT be copied into proof artifacts; where an implementation does reproduce or adapt OWASP text, that material is subject to CC BY-SA 4.0 and MUST be attributed and licensed accordingly, separately from Proof Protocol material.

## 8. Framework-Agnostic Architecture

> **Threat frameworks are pluggable inputs to Proof Protocol. Proof Protocol is framework-agnostic.**

External frameworks can identify **what to test**: threats, vulnerabilities, techniques, risk categories, controls, design assertions, identity claims, tool permissions, or other risk conditions. Proof Protocol independently establishes **whether the control worked and what evidence proves that result**.

No external framework is required for Proof Protocol to operate. A Proof Protocol implementation MAY use the OWASP Top 10 for LLM Applications, the OWASP Top 10 for Agentic Applications, MITRE ATLAS, CSA MAESTRO, AIVSS, a proprietary threat model, another recognized framework, or no external framework at all when the test condition is otherwise sufficiently defined.

Adding, replacing, muting, or removing a framework mapping does not alter the Proof Protocol architecture, evidence model, Proof of Efficacy determination, ProofBundle™, ProofStamp™, ProofRegister™, or independent corroboration requirements.

A framework mapping therefore establishes **interoperability**, not architectural dependency.

## 9. Relationship to Proof Protocol

This mapping is part of the Proof Protocol specification family maintained by Nebulonium, Inc.

The relationship is intentionally asymmetric:

> **OWASP supplies LLM application risk context. Proof Protocol supplies the evidence model for determining whether a selected defensive control performed as claimed.**

No affiliation, endorsement, certification, or sponsorship by OWASP is implied.

## 10. Source Framework, Attribution, and License

The OWASP Top 10 for LLM Applications is external work of the OWASP GenAI Security Project, published by the OWASP Foundation. OWASP names, risk identifiers, trademarks, and expressive framework content remain subject to OWASP's applicable terms.

The OWASP GenAI Security Project site (https://genai.owasp.org/llm-top-10/) states: "Unless otherwise specified, all content on the site is Creative Commons Attribution-ShareAlike v4.0 and provided without warranty of service or accuracy." The project source repository (https://github.com/GenAI-Security-Project/GenAI-LLM-Top10) names the Creative Commons Attribution-ShareAlike 4.0 International License (CC BY-SA 4.0). CC BY-SA 4.0 is a ShareAlike license: adapted material that reproduces or modifies OWASP text would have to be distributed under CC BY-SA 4.0 or a compatible license.

This Proof Protocol mapping is independently authored and Licensed under the Greater Good Commercial License 1.0 (see LICENSE.md); text CC BY-ND 4.0 under its Part S. Original inventor: Craig Thomas Ellrod (ORCID 0009-0004-1058-7666).

### Required attribution

CC BY-SA 4.0 requires attribution when OWASP material is shared or adapted. The OWASP repository README supplies citation metadata (author: OWASP GenAI Security Project; year: 2026; title: OWASP Top 10 for Large Language Model Applications; version: 2026; publisher: OWASP Foundation; version DOI: 10.5281/zenodo.22109015). The following attribution, built from that metadata, is used:

> OWASP Top 10 for Large Language Model Applications, Version 2026, OWASP GenAI Security Project, OWASP Foundation, https://doi.org/10.5281/zenodo.22109015 (https://genai.owasp.org/llm-top-10/), Licensed under the Greater Good Commercial License 1.0 (see LICENSE.md); text CC BY-ND 4.0 under its Part S. Original inventor: Craig Thomas Ellrod (ORCID 0009-0004-1058-7666).

The OWASP site carries the following trademark statement, quoted verbatim:

> OWASP and the OWASP logo are trademarks of the OWASP Foundation, Inc.

This specification reproduces only the project name, the edition, the identifier format, and short factual statements about the project. It does not reproduce, paraphrase at length, or adapt OWASP risk descriptions, examples, prevention guidance, or attack scenarios, so it is not an adaptation of OWASP material and the CC BY-SA 4.0 ShareAlike condition is not triggered. This specification does not use OWASP logos.

## 11. Versioning

This mapping is versioned independently of the OWASP Top 10 for LLM Applications. This version was prepared against the 2026 edition. Implementations MAY map to the 2025 edition where required, provided the edition is recorded with each identifier. Material upstream changes SHOULD trigger a mapping review and, where necessary, a new version identifying the OWASP edition mapped.

---

*Proof Protocol · proofprotocol.io · CC BY 4.0*
