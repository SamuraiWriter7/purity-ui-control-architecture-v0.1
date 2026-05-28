# Royalty OS Visibility

## 1. Purpose

This document defines the **Royalty OS Visibility** layer for Purity UI Control Architecture v0.1.

The purpose of this layer is to show how trace, reference, contribution, and allocation-readiness signals may be displayed in a creator-controlled platform interface.

This layer does not define final payment.

It does not determine legal ownership.

It does not assign royalty entitlement.

It only defines how royalty-related visibility may appear in a platform UI without collapsing trace evidence, allocation readiness, and payment execution into a single automatic process.

---

## 2. Core Problem

AI-mediated platforms may increasingly reference, summarize, retrieve, or reuse creator works.

These uses may create trace signals such as:

* AI retrieval events
* RAG references
* platform AI references
* AI search references
* summary references
* citation-like references
* influence-like references
* downstream reuse events

Creators may reasonably want to know:

```text
Was my work referenced?
How often was it referenced?
By what kind of AI system?
At what depth was it used?
Did it contribute to downstream outputs?
Could this become relevant for future value circulation?
```

However, showing these signals can easily create misunderstanding.

A trace signal is not the same as a payment claim.

A contribution score is not the same as ownership.

An estimated preview is not the same as guaranteed compensation.

Royalty OS Visibility exists to show value-circulation signals carefully and transparently.

---

## 3. Core Principle

The central principle of Royalty OS Visibility is:

> Show trace-to-allocation-readiness signals without implying guaranteed payment.

This layer must clearly separate:

```text
Trace evidence
↓
Contribution signal
↓
Allocation-readiness preview
↓
Human or multi-wing review
↓
Final allocation decision
↓
Payment execution
```

Only the first three are part of this visibility layer.

Final allocation and payment execution are outside the scope of this document.

---

## 4. What This Layer May Display

Royalty OS Visibility may display:

* trace events
* AI reference history
* reference depth
* contribution score
* allocation-readiness status
* estimated preview
* review status
* dispute status
* redacted explanation
* source categories
* relevant circle versions
* visibility restrictions
* required disclaimers

Example reader-facing display:

```text
Royalty OS Preview

Trace contribution score: 4.1
Allocation-readiness status: Review required
Estimated preview: ¥128
Guaranteed: No

This preview is an estimation only.
It does not guarantee payment, ownership, entitlement, or final allocation.
```

---

## 5. What This Layer Must Not Display as Final

Royalty OS Visibility must not present the following as final truth:

* final royalty entitlement
* guaranteed payment
* legal ownership
* copyright claim
* authorship proof
* final allocation percentage
* binding compensation amount
* undisputed contribution rank
* complete value attribution

Recommended warning:

```text
This preview is not a payment decision.
```

The UI should avoid language such as:

```text
You earned this amount.
You are owed this amount.
This is your final royalty.
This proves ownership.
This guarantees allocation.
```

Unless such claims are supported by a separate legal, contractual, or payment system, they should not appear in this layer.

---

## 6. Royalty Visibility Object

A basic object may look like this:

```yaml
royalty_visibility:
  enabled: true
  visibility: public
  allocation_readiness: review_required
  trace_contribution_score: 4.1
  estimated_preview:
    amount: 128
    currency: JPY
    guaranteed: false
  show_disclaimer: true
  disclaimer_required: true
```

Recommended fields:

| Field                      | Description                              |
| -------------------------- | ---------------------------------------- |
| `enabled`                  | Whether Royalty OS visibility is enabled |
| `visibility`               | Visibility level for the royalty preview |
| `allocation_readiness`     | Review-readiness state                   |
| `trace_contribution_score` | Non-final contribution signal            |
| `estimated_preview`        | Estimated preview object                 |
| `show_disclaimer`          | Whether the UI displays a disclaimer     |
| `disclaimer_required`      | Whether disclaimer is mandatory          |

---

## 7. Allocation-Readiness Status

Recommended status values:

| Status                       | Meaning                                    |
| ---------------------------- | ------------------------------------------ |
| `not_applicable`             | No royalty-readiness display applies       |
| `eligible_for_review`        | Trace signals may support review           |
| `review_required`            | Human or multi-wing review is required     |
| `blocked`                    | Transition to allocation review is blocked |
| `disputed`                   | Signal or claim is under dispute           |
| `insufficient_evidence`      | Evidence is too weak for review            |
| `pending_trace_confirmation` | Trace data requires confirmation           |

Example:

```yaml
royalty_visibility:
  allocation_readiness: review_required
```

The status should never be interpreted as automatic payment.

---

## 8. Estimated Preview

Estimated preview may display a possible value, range, or placeholder.

Example:

```yaml
estimated_preview:
  amount: 128
  currency: JPY
  guaranteed: false
  calculation_basis: trace_contribution_score
```

Alternative range format:

```yaml
estimated_preview:
  range:
    minimum: 50
    maximum: 180
  currency: JPY
  guaranteed: false
```

Required rule:

```text
estimated_preview.guaranteed must be false unless an external payment system has confirmed final execution.
```

Recommended default:

```yaml
guaranteed: false
```

---

## 9. Required Disclaimer

Any UI showing royalty-related estimation must include a clear disclaimer.

Recommended text:

```text
This preview is an estimation only.
It does not guarantee payment, ownership, entitlement, or final allocation.
```

Short version:

```text
Estimated preview only. Not a guaranteed payment.
```

Japanese UI equivalent:

```text
これは試算表示です。
実際の支払い・所有権・権利配分・最終分配を保証するものではありません。
```

The disclaimer should be visible near the estimated preview.

It should not be hidden only in a terms-of-service document.

---

## 10. Trace Contribution Score

A trace contribution score may indicate the relative strength of trace-based contribution signals.

Example:

```yaml
trace_contribution_score: 4.1
```

This score may be based on:

* number of references
* depth of reference
* type of reference
* recency
* citation visibility
* RAG retrieval context
* platform AI usage
* source confidence
* circle version relevance
* dispute status

However, this score is not final allocation.

Recommended label:

```text
Trace contribution score
```

Avoid:

```text
Royalty score
Final value score
Payment score
Ownership score
```

The word "contribution" is safer than "entitlement."

---

## 11. Reference Depth

Reference depth may describe how deeply a work was used.

Possible levels:

| Level                  | Description                            |
| ---------------------- | -------------------------------------- |
| `surface_reference`    | Minimal reference or shallow mention   |
| `summary_reference`    | Used for summarization                 |
| `context_reference`    | Used as context in a generated answer  |
| `structural_reference` | Influenced structure or framing        |
| `core_reference`       | Central reference in downstream output |

Example:

```yaml
reference_depth:
  level: structural_reference
  confidence: 0.74
```

Reference depth should be treated as a review signal, not a final payment rule.

---

## 12. Source Categories

Royalty OS Visibility may show broad source categories instead of exact system names.

Example:

```yaml
source_categories:
  - ai_search
  - rag_system
  - platform_ai_editor
```

Possible categories:

```text
ai_search
rag_system
platform_ai_editor
summary_tool
citation_tool
training_pipeline
evaluation_pipeline
external_agent
unknown
```

If exact system names are sensitive or unavailable, the UI may display categories only.

Example display:

```text
Referenced by: AI search / RAG system / platform AI editor
```

---

## 13. Relationship to Trace Visibility

Royalty OS Visibility depends on trace visibility but is not identical to it.

Trace Visibility answers:

```text
Was this work referenced or reused?
```

Royalty OS Visibility answers:

```text
Could those trace signals support future allocation-readiness review?
```

Recommended relationship:

```text
Trace Event
↓
Trace Visibility
↓
Contribution Signal
↓
Allocation-Readiness Preview
↓
Royalty OS Visibility
```

Trace evidence should remain separate from payment decisions.

---

## 14. Relationship to Visibility Protocol

Royalty OS Visibility must respect the Visibility Protocol.

Example:

```yaml
visibility_protocol:
  deep_layer: private
  trace_log: public
  royalty_preview: public
```

This means:

* trace and royalty preview may be shown
* deep layer must remain hidden
* royalty explanation must not reveal private deep-layer context

If royalty explanation depends on private fields, the UI should use redacted explanation.

Example:

```text
Contribution signal detected.
Private origin context is protected and not displayed.
```

---

## 15. Relationship to No-Inference Layer

Royalty-related explanations must not infer protected private context.

Example:

```yaml
no_inference_policy:
  enabled: true
  protected_fields:
    - deep_layer
    - private_creator_note
  prohibited_actions:
    - reconstruct_private_context
    - summarize_protected_fields
```

If this policy is active, Royalty OS Visibility should avoid explaining contribution based on protected fields.

Allowed display:

```text
Trace contribution signal detected from authorized public reference.
```

Avoid:

```text
This contribution likely comes from the creator's private emotional background.
```

unless explicitly permitted.

---

## 16. Relationship to Circle Versioning

Royalty-related review may depend on the circle version active at the time of reference.

Example:

```yaml
royalty_visibility:
  relevant_circle_versions:
    - circle_v0.1
    - circle_v0.2
```

Trace event example:

```yaml
trace_event:
  id: trace_001
  referenced_at: "2026-05-29T12:00:00Z"
  circle_version_at_reference: circle_v0.2
```

This helps distinguish:

```text
what was visible then
vs.
what is visible now
```

If a creator later changes visibility settings, old trace events should not silently override current restrictions.

---

## 17. Relationship to Epicenter Layer

The Epicenter Layer may help reviewers understand the origin structure of a work.

However, epicenter data must not be used as automatic royalty entitlement.

Recommended separation:

```text
Epicenter Layer
↓
Trace Evidence
↓
Contribution Signal
↓
Allocation Readiness
↓
Review
```

The Epicenter Layer may support review.

It should not automatically determine payment.

---

## 18. Relationship to AI Purity Detection

AI Purity Detection may provide origin-purity signals.

These signals may be relevant to allocation-readiness review.

However:

```text
origin_purity_score
≠
royalty entitlement
```

Purity may help answer:

```text
Does the work preserve human-origin signals?
```

Royalty OS Visibility may help answer:

```text
Are there trace signals that may support review?
```

Neither should automatically answer:

```text
How much should be paid?
```

---

## 19. Reader-Facing UI

Reader-facing UI should remain simple.

Possible display:

```text
Royalty OS Preview

AI reference signals detected.
Allocation-readiness: Review required.
Estimated preview: ¥128
Guaranteed: No

This preview is an estimation only.
```

Reader-facing UI should not expose:

* private creator notes
* protected deep-layer context
* hidden trace reasoning
* private dispute details
* internal payment logic
* confidential platform calculations

---

## 20. Creator-Facing UI

Creator-facing UI may show more detail.

Possible controls:

```text
Royalty OS Visibility

[x] Show trace contribution score
[x] Show allocation-readiness status
[x] Show estimated preview
[x] Show disclaimer
[ ] Show exact AI system names
[ ] Show private contribution reasoning
```

Creator-facing settings may include:

```yaml
royalty_visibility_controls:
  show_trace_contribution_score: true
  show_allocation_readiness: true
  show_estimated_preview: true
  show_exact_system_names: false
  show_private_reasoning: false
  require_disclaimer: true
```

---

## 21. Dispute Status

Royalty OS Visibility should support dispute-aware display.

Possible dispute statuses:

| Status                 | Meaning                                         |
| ---------------------- | ----------------------------------------------- |
| `none`                 | No dispute                                      |
| `pending_review`       | Under review                                    |
| `creator_disputed`     | Creator disputes the trace or allocation signal |
| `platform_disputed`    | Platform disputes the signal                    |
| `third_party_disputed` | External party disputes the signal              |
| `resolved`             | Dispute resolved                                |
| `blocked`              | Display or transition blocked due to dispute    |

Example:

```yaml
dispute_status:
  state: pending_review
  summary: "Contribution signal requires review before allocation-readiness can proceed."
```

Reader-facing display should be minimal:

```text
Status: Under review
```

Creator-facing display may show more detail.

---

## 22. Redaction Rules

Royalty OS Visibility must support redaction.

Redaction may apply when:

* trace evidence references private content
* contribution explanation depends on protected fields
* source identity is restricted
* dispute information is sensitive
* circle version contains private fields
* No-Inference Policy blocks explanation

Example:

```yaml
redaction:
  enabled: true
  reason: protected_creator_context
  public_message: "Some contribution details are hidden due to creator privacy settings."
```

Recommended principle:

```text
Show that a signal exists without exposing protected context.
```

---

## 23. Example Full Royalty Visibility Object

```yaml
royalty_visibility:
  enabled: true
  visibility: public

  trace_contribution_score: 4.1
  allocation_readiness: review_required

  estimated_preview:
    amount: 128
    currency: JPY
    guaranteed: false
    calculation_basis: trace_contribution_score

  reference_depth:
    level: structural_reference
    confidence: 0.74

  source_categories:
    - ai_search
    - rag_system
    - platform_ai_editor

  relevant_circle_versions:
    - circle_v0.2

  dispute_status:
    state: none

  redaction:
    enabled: true
    reason: protected_creator_context
    public_message: "Some contribution details are hidden due to creator privacy settings."

  disclaimer_required: true
  required_disclaimer: >
    This preview is an estimation only. It does not guarantee payment,
    ownership, entitlement, or final allocation.
```

---

## 24. Design Principles

### 24.1 Estimation, Not Entitlement

Royalty-related UI must not imply final payment.

### 24.2 Trace Before Allocation

Trace evidence should be visible before allocation is considered.

### 24.3 Review Before Payment

Human or multi-wing review should remain separate from automatic display.

### 24.4 Privacy by Default

Royalty explanations must not expose private creator context.

### 24.5 Dispute Awareness

Disputed signals should be marked clearly.

### 24.6 Redaction Support

Protected fields should be redacted or summarized safely.

### 24.7 Creator Control

Creators should decide whether royalty preview is shown publicly.

---

## 25. Non-Goals

Royalty OS Visibility does not attempt to:

* determine final payment
* guarantee compensation
* define royalty rates
* determine legal ownership
* prove authorship
* replace contracts
* replace payment processors
* define tax treatment
* resolve disputes automatically
* expose private creator context
* override Visibility Protocol
* override No-Inference Policy
* replace Royalty OS itself

This layer is a visibility and preview layer only.

---

## 26. Summary

Royalty OS Visibility defines how trace-to-allocation-readiness signals may appear in a creator-controlled UI.

It connects:

```text
trace events
↓
reference depth
↓
contribution signal
↓
allocation-readiness status
↓
estimated preview
↓
review / dispute awareness
```

Its central principle is:

> Show the possibility of value circulation without pretending that estimation is payment.

In Purity UI Control Architecture, this layer helps creators see how AI references may connect to future value circulation while preserving privacy, review, and governance boundaries.
