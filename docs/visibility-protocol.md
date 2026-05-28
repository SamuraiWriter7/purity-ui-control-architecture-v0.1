# Visibility Protocol

## 1. Purpose

This document defines the **Visibility Protocol** for Purity UI Control Architecture v0.1.

The purpose of the Visibility Protocol is to provide creator-controlled access rules for human-origin meaning structures in AI-mediated platforms.

A simple public/private switch is not enough in AI-era content systems.

Creators may need to decide:

* what human readers can see
* what AI systems can read
* what AI systems may summarize
* what should remain private
* what may be exposed only as abstract friction
* what may be used for trace or royalty-readiness systems
* what must never be inferred, reconstructed, or trained on

The Visibility Protocol provides a structured way to define these boundaries.

---

## 2. Core Problem

Traditional platforms usually provide simple visibility options:

```text
public
private
limited sharing
```

This was sufficient when the main audience was human readers.

However, AI-mediated platforms introduce new access modes.

A work may be:

* read by human readers
* retrieved by AI search
* summarized by AI tools
* embedded into RAG systems
* analyzed for source integrity
* referenced in downstream AI outputs
* included in trace logs
* considered for royalty-readiness review
* exposed to platform-level recommendation systems
* used, directly or indirectly, for training or evaluation

Because of this, visibility must become more precise.

The question is no longer only:

```text
Can people see this?
```

The question becomes:

```text
Who or what may access this layer,
for what purpose,
at what level of detail,
and under what restrictions?
```

---

## 3. Core Principle

The central principle of the Visibility Protocol is:

> Creator-defined visibility boundaries must remain authoritative.

AI systems may assist, retrieve, summarize, or classify only within the creator-defined visibility boundary.

Visibility should not be silently expanded by:

* platform defaults
* AI inference
* search indexing
* RAG ingestion
* summarization tools
* training pipelines
* recommendation systems
* royalty-readiness systems

If the creator defines a field as private, AI systems should not reconstruct it from nearby context.

If the creator defines a field as summary-only, AI systems should not expose the full content.

If the creator defines a field as friction-only, AI systems should not infer the full personal story behind it.

---

## 4. Visibility Levels

The Visibility Protocol defines five primary visibility levels.

| Level | Label         | Description                                                    |
| ----- | ------------- | -------------------------------------------------------------- |
| 1     | Public        | Visible to human readers and AI systems                        |
| 2     | AI-Readable   | Hidden from public UI, readable by authorized AI systems       |
| 3     | Summary-Only  | Only a summary may be used by AI systems                       |
| 4     | Friction-Only | Only the friction category or abstract signal may be disclosed |
| 5     | Private       | Not visible to readers or AI systems                           |

---

## 5. Level 1: Public

### Definition

`public` means the field may be displayed to human readers and accessed by AI systems.

### Intended Use

This level may be used for:

* article title
* public summary
* public core question
* public tags
* public trace summary
* creator-approved notes
* public Purity badge
* public relationship indicators

### Example

```yaml
visibility_protocol:
  article_title: public
  core_question: public
  purity_badge: public
```

### Notes

Public does not mean unrestricted downstream use.

Even if a field is public, platform policies may still define limits for:

* training use
* commercial reuse
* attribution
* trace logging
* royalty-readiness review

---

## 6. Level 2: AI-Readable

### Definition

`ai_readable` means the field is hidden from public reader-facing UI, but may be accessed by authorized AI systems.

### Intended Use

This level may be used when creators want AI systems to understand context without exposing it publicly.

Possible examples:

* internal semantic hints
* creator-defined interpretation notes
* platform moderation context
* structured metadata
* non-public but AI-readable source notes
* machine-readable access hints

### Example

```yaml
visibility_protocol:
  interpretation_boundary: ai_readable
  creator_defined_scope: ai_readable
```

### Required Restrictions

AI-readable fields should have clear constraints.

AI systems may be allowed to:

* read
* classify
* index under permitted rules
* use for context-aware display
* use for internal review routing

AI systems should not automatically:

* reveal the field to readers
* quote the field
* train on the field
* infer private context beyond the field
* expose it in generated outputs

### Notes

AI-readable should not become a hidden backdoor for unrestricted platform use.

It must remain creator-controlled.

---

## 7. Level 3: Summary-Only

### Definition

`summary_only` means the full field should not be exposed, but a summarized version may be used.

### Intended Use

This level may be used for:

* sensitive background context
* long private notes
* meaning-layer summaries
* deep-layer abstraction
* limited AI-readable summaries
* platform-level safety descriptions

### Example

```yaml
visibility_protocol:
  rotation_dynamics: summary_only
  deep_context_summary: summary_only
```

### Example Output

The full creator note may be private, but the platform may show:

```text
This article emerged from a personal productivity-related friction.
```

instead of exposing the full private background.

### Required Restrictions

AI systems should not:

* expose the full field
* reconstruct the full field
* infer details beyond the approved summary
* generate psychological or biographical profiles
* use summary-only fields as training data without explicit permission

### Notes

Summary-only is useful when creators want to preserve meaning context while avoiding unnecessary exposure.

---

## 8. Level 4: Friction-Only

### Definition

`friction_only` means only the category or abstract type of friction may be disclosed.

The underlying content remains hidden.

### Intended Use

This level is useful for protecting early-stage or sensitive human-origin signals.

Possible friction categories:

* emotion
* body_sensation
* social_conflict
* cognitive_dissonance
* unresolved_question
* field_observation
* creative_pressure
* ethical_discomfort
* silence
* other

### Example

```yaml
visibility_protocol:
  initial_friction: friction_only
```

### Example Output

The public UI may show:

```text
Initial Friction: emotional discomfort
```

But it should not show:

```text
The creator felt frustration because of a specific private life event.
```

unless explicitly permitted.

### Required Restrictions

AI systems should not:

* reconstruct the hidden story
* infer private events from the friction category
* convert friction into diagnosis
* expose personal details
* summarize protected background context

### Notes

Friction-only is one of the most important visibility levels.

It allows human-origin signals to remain visible without exposing personal or sensitive details.

---

## 9. Level 5: Private

### Definition

`private` means the field is not visible to human readers or AI systems.

### Intended Use

This level should be used for:

* private creator notes
* deep-layer context
* unresolved friction
* sensitive personal background
* protected meaning boundaries
* non-public interpretation notes
* fields restricted by no-inference policy

### Example

```yaml
visibility_protocol:
  deep_layer: private
  private_creator_note: private
  proto_friction: private
```

### Required Restrictions

Private fields should not be:

* displayed
* quoted
* summarized
* indexed for public retrieval
* used for training
* reconstructed by AI
* inferred from surrounding fields
* exposed through trace or royalty UI

### Notes

Private should be the default for sensitive semantic-origin fields.

The system should not pressure creators to disclose private fields for higher visibility, better scoring, or platform advantage.

---

## 10. Field-Level Visibility

Visibility should be defined at the field level.

A single work may contain multiple fields with different visibility levels.

Example:

```yaml
visibility_protocol:
  article_title: public
  core_question: public
  initial_friction: friction_only
  deep_layer: private
  rotation_dynamics: summary_only
  interpretation_boundary: ai_readable
  trace_log: public
  royalty_preview: public
  private_creator_note: private
```

This allows the creator to define a layered disclosure structure.

---

## 11. Default Visibility Recommendations

Recommended default settings:

| Field                     | Recommended Default               |
| ------------------------- | --------------------------------- |
| `article_title`           | public                            |
| `public_summary`          | public                            |
| `core_question`           | private or public, creator choice |
| `initial_friction`        | friction_only                     |
| `proto_friction`          | private                           |
| `deep_layer`              | private                           |
| `private_creator_note`    | private                           |
| `rotation_dynamics`       | summary_only                      |
| `interpretation_boundary` | ai_readable                       |
| `trace_log`               | private or public, creator choice |
| `royalty_preview`         | private or public, creator choice |
| `no_inference_policy`     | ai_readable                       |
| `training_permission`     | private / explicit opt-in         |

The safest default is:

> Sensitive meaning-origin fields should be private by default.

---

## 12. Relationship to No-Inference Layer

Visibility and inference control are related but not identical.

Visibility defines:

```text
Who or what may access a field?
```

No-Inference defines:

```text
What may AI systems not infer, reconstruct, or generate from that field?
```

Example:

```yaml
visibility_protocol:
  initial_friction: friction_only
  deep_layer: private

no_inference_policy:
  enabled: true
  protected_fields:
    - initial_friction
    - deep_layer
  prohibited_actions:
    - infer_intent
    - reconstruct_private_context
    - summarize_protected_fields
```

A field may be partially visible but still inference-protected.

For example:

```text
Initial Friction: ethical discomfort
```

may be visible, but AI must not infer the specific private situation behind it.

---

## 13. Relationship to AI Training Use

Visibility does not automatically grant training permission.

A field may be public but not allowed for training.

Training permission should be handled separately.

Example:

```yaml
training_permission:
  allowed: false
  applies_to:
    - article_body
    - core_question
    - initial_friction
    - deep_layer
```

The principle is:

> Public visibility is not the same as training consent.

This distinction is essential for creator sovereignty.

---

## 14. Relationship to Trace Visibility

Trace visibility controls whether reference or reuse logs are displayed.

Trace logs may include:

* AI retrieval events
* RAG references
* platform AI references
* citation-like references
* influence-like references
* royalty-readiness signals

Example:

```yaml
trace_visibility:
  enabled: true
  visibility: public
  show_reference_depth: true
  show_ai_system_category: true
  show_exact_system_name: false
```

Trace visibility should not reveal private creator fields.

If a trace event references private content, the displayed trace should be redacted or summarized.

---

## 15. Relationship to Royalty OS Visibility

Royalty OS-related displays must respect visibility settings.

A creator may allow:

* trace visibility
* royalty-readiness preview
* estimated allocation preview
* review status visibility

But these displays must not expose private semantic-origin fields.

Example:

```yaml
royalty_visibility:
  enabled: true
  visibility: public
  show_estimated_preview: true
  show_disclaimer: true
```

Required disclaimer:

```text
This preview is an estimation only.
It does not guarantee payment, ownership, entitlement, or final allocation.
```

---

## 16. Visibility and Circle Versioning

Visibility settings may change over time.

For this reason, visibility updates should be versioned.

Example:

```yaml
circle_version:
  id: circle_v0.3
  previous_version: circle_v0.2
  change_type:
    - visibility_update
  summary: "Initial friction changed from private to friction_only."
```

Versioning helps preserve accountability.

It also prevents confusion when older AI references were made under different visibility rules.

---

## 17. Visibility Conflict Handling

Conflicts may occur when different settings overlap.

Examples:

```text
core_question = public
no_inference_policy protects core_question

trace_log = public
but trace references private deep_layer

royalty_preview = public
but contribution explanation depends on private fields

AI-readable field
but training permission is false
```

Recommended conflict resolution:

```text
Most restrictive rule wins.
```

If a field is private, no other setting should expose it.

If training permission is false, visibility should not override that.

If no-inference policy protects a field, AI should not infer beyond the permitted boundary.

---

## 18. Example Full Visibility Object

```yaml
visibility_protocol:
  article_title: public
  public_summary: public
  core_question: public
  initial_friction: friction_only
  proto_friction: private
  deep_layer: private
  rotation_dynamics: summary_only
  interpretation_boundary: ai_readable
  private_creator_note: private

trace_visibility:
  enabled: true
  visibility: public
  show_reference_depth: true
  show_ai_system_category: true
  show_exact_system_name: false

royalty_visibility:
  enabled: true
  visibility: public
  show_estimated_preview: true
  show_disclaimer: true

training_permission:
  allowed: false
  applies_to:
    - article_body
    - core_question
    - initial_friction
    - deep_layer

no_inference_policy:
  enabled: true
  protected_fields:
    - initial_friction
    - deep_layer
    - private_creator_note
  prohibited_actions:
    - infer_intent
    - reconstruct_private_context
    - summarize_protected_fields
    - use_for_training
```

---

## 19. Non-Goals

The Visibility Protocol does not attempt to:

* define a complete legal consent framework
* replace copyright law
* define final platform policy
* guarantee enforcement by all AI systems
* replace access-control infrastructure
* determine royalty entitlement
* determine authorship
* rank creators by visibility level
* force creators to disclose private context
* make private fields usable by AI through inference

This protocol is a draft design layer for creator-controlled disclosure in AI-mediated platforms.

---

## 20. Summary

The Visibility Protocol defines how creator-controlled meaning structures may be disclosed, hidden, summarized, or restricted.

Its main levels are:

```text
Public
AI-Readable
Summary-Only
Friction-Only
Private
```

Its central principle is:

> Public visibility, AI readability, summarization, training permission, and inference permission are different things.

The goal is to let creators define not only what is shown, but also what AI may read, summarize, infer, or reuse.

In AI-mediated platforms, visibility is no longer a simple switch.

It is a governance layer.
