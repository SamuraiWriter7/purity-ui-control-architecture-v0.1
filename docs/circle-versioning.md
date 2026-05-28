# Circle Versioning

## 1. Purpose

This document defines **Circle Versioning** for Purity UI Control Architecture v0.1.

The purpose of Circle Versioning is to track how a creator's meaning structure evolves over time.

A creator's friction, question, interpretation boundary, visibility settings, and AI-access permissions may change.

Without versioning, platforms may freeze a creator's early thought into a fixed identity.

Circle Versioning prevents this.

It allows meaning structures to evolve while preserving their history.

---

## 2. Core Problem

Traditional platforms usually treat content as a static object.

An article is published.

A post is displayed.

A page is edited.

A version may exist internally, but the meaning structure behind the work is rarely tracked.

In AI-mediated platforms, this becomes a problem.

AI systems may read, summarize, index, retrieve, or reuse a work at different points in time.

But the creator's meaning boundary may have changed.

For example:

* an initial discomfort becomes a clear question
* a private friction becomes friction-only public
* a public question becomes restricted
* a meaning boundary becomes more precise
* AI training permission changes
* a No-Inference Policy becomes active
* a Trace or Royalty visibility setting changes

Without versioning, AI systems may apply outdated interpretation rules to a changed meaning structure.

Circle Versioning provides a way to preserve these transitions.

---

## 3. Core Principle

The central principle of Circle Versioning is:

> A creator's meaning structure should be allowed to evolve.

A creator should not be permanently bound to an early version of their thought.

At the same time, changes should be traceable.

Circle Versioning balances two needs:

```text
evolution
+
accountability
```

The creator may change the circle.

The system should preserve the history of the change.

---

## 4. What Is a Circle?

In this architecture, a circle represents a creator-defined meaning structure.

A circle may include:

* proto-friction
* friction layer
* question layer
* meaning layer
* visibility settings
* no-inference settings
* trace visibility
* royalty-readiness visibility
* creator notes
* interpretation boundaries

A circle is not merely a visual symbol.

It is a structured origin object.

It represents how a work's meaning is organized, protected, and disclosed.

---

## 5. What Is a Circle Version?

A circle version is a recorded state of the meaning structure at a specific point in time.

Example:

```yaml
circle_version:
  id: circle_v0.1
  created_at: "2026-05-28T00:00:00Z"
  status: active
```

A later version may change the question, visibility, or AI permissions:

```yaml
circle_version:
  id: circle_v0.2
  previous_version: circle_v0.1
  created_at: "2026-05-29T00:00:00Z"
  change_type:
    - question_refinement
    - visibility_update
  summary: "The original emotional friction evolved into a design question."
```

---

## 6. Version Identifier

Recommended version identifier format:

```text
circle_v0.1
circle_v0.2
circle_v0.3
```

Alternative formats may include:

```text
circle_2026_05_28_001
circle_alpha_001
circle_revision_001
```

Recommended default:

```text
circle_vX.Y
```

This keeps the version easy to read in both UI and metadata.

---

## 7. Version Object

A basic Circle Version object may include:

```yaml
circle_version:
  id: circle_v0.2
  previous_version: circle_v0.1
  created_at: "2026-05-29T00:00:00Z"
  change_type:
    - question_refinement
    - visibility_update
  summary: "The original discomfort became a clearer question about creator-controlled AI access."
  changed_by: creator
  status: active
```

Recommended fields:

| Field              | Description                              |
| ------------------ | ---------------------------------------- |
| `id`               | Version identifier                       |
| `previous_version` | Previous circle version                  |
| `created_at`       | Version creation timestamp               |
| `change_type`      | Type of change                           |
| `summary`          | Human-readable description of the change |
| `changed_by`       | Who initiated the change                 |
| `status`           | Current status of the version            |

---

## 8. Change Types

Recommended `change_type` values:

| Change Type                   | Meaning                                                   |
| ----------------------------- | --------------------------------------------------------- |
| `initial_record`              | First recorded circle                                     |
| `proto_friction_update`       | Proto-friction was added, changed, archived, or converted |
| `friction_update`             | Friction layer changed                                    |
| `question_refinement`         | Core or sub-questions changed                             |
| `meaning_boundary_update`     | Meaning boundary changed                                  |
| `visibility_update`           | Visibility settings changed                               |
| `no_inference_policy_update`  | No-Inference Policy changed                               |
| `trace_policy_update`         | Trace visibility or trace rules changed                   |
| `royalty_visibility_update`   | Royalty OS visibility settings changed                    |
| `training_permission_update`  | AI training permission changed                            |
| `creator_note_update`         | Creator notes changed                                     |
| `network_relationship_update` | Epicenter network relationships changed                   |
| `archival_update`             | Version archived or deprecated                            |
| `dispute_related_update`      | Change related to dispute, correction, or review          |

Example:

```yaml
change_type:
  - proto_friction_update
  - question_refinement
  - no_inference_policy_update
```

---

## 9. Version Status

Recommended status values:

| Status       | Meaning                                   |
| ------------ | ----------------------------------------- |
| `draft`      | Version exists but is not active          |
| `active`     | Current active version                    |
| `archived`   | Preserved but no longer active            |
| `superseded` | Replaced by a newer version               |
| `deprecated` | Should not be used for new interpretation |
| `disputed`   | Under review or dispute                   |
| `reaffirmed` | Explicitly confirmed by the creator       |

Example:

```yaml
circle_version:
  id: circle_v0.1
  status: superseded
```

---

## 10. Why Versioning Matters

Circle Versioning matters because AI systems may access a work at different times.

Example:

```text
Day 1:
Core Question is private.

Day 5:
Core Question becomes public.

Day 10:
Deep Layer becomes private again.

Day 20:
No-Inference Policy is added.
```

If AI accessed the work on Day 5, it may have had different permissions than on Day 20.

Versioning helps answer:

```text
Which visibility settings were active at the time of access?
Which No-Inference rules applied?
Which meaning boundary was valid?
Was the trace created before or after a policy change?
```

Without versioning, platform accountability becomes weak.

---

## 11. Relationship to Proto-Friction Layer

Proto-friction often evolves over time.

Possible flow:

```text
proto_friction unresolved
↓
proto_friction partially verbalized
↓
friction_layer defined
↓
core_question formed
↓
meaning_boundary defined
```

Circle Versioning can record this evolution.

Example:

```yaml
circle_version:
  id: circle_v0.2
  previous_version: circle_v0.1
  change_type:
    - proto_friction_update
    - question_refinement
  summary: "Unresolved discomfort became a clearer question about AI summarization."
```

This prevents the final question from erasing the earlier uncertainty that produced it.

---

## 12. Relationship to Epicenter Layer

The Epicenter Layer defines the structure:

```text
friction
↓
question
↓
meaning
```

Circle Versioning tracks how that structure changes.

Example:

```yaml
epicenter:
  id: epicenter_001
  current_circle_version: circle_v0.3

circle_versions:
  - id: circle_v0.1
    summary: "Initial friction recorded."
  - id: circle_v0.2
    summary: "Core question refined."
  - id: circle_v0.3
    summary: "Meaning boundary updated."
```

The Epicenter Layer answers:

```text
What is the meaning structure?
```

Circle Versioning answers:

```text
How has the meaning structure changed?
```

---

## 13. Relationship to Visibility Protocol

Visibility settings may change over time.

For example:

```yaml
circle_version:
  id: circle_v0.1
  visibility_protocol:
    core_question: private
    initial_friction: private
```

Later:

```yaml
circle_version:
  id: circle_v0.2
  previous_version: circle_v0.1
  visibility_protocol:
    core_question: public
    initial_friction: friction_only
```

This matters because access permissions depend on the active version.

If a trace event occurred under `circle_v0.1`, the system should not retroactively treat it as if `circle_v0.2` permissions applied.

---

## 14. Relationship to No-Inference Layer

No-Inference Policies may also change over time.

Example:

```yaml
circle_version:
  id: circle_v0.3
  change_type:
    - no_inference_policy_update
  no_inference_policy:
    enabled: true
    protected_fields:
      - initial_friction
      - deep_layer
    prohibited_actions:
      - infer_intent
      - reconstruct_private_context
```

A work may have been open to AI interpretation earlier, but later restricted.

Versioning allows the platform to record:

* when the restriction was added
* what fields became protected
* which AI actions became prohibited
* which trace events occurred before or after the restriction

---

## 15. Relationship to Trace Visibility

Trace logs should reference the applicable circle version.

Example:

```yaml
trace_event:
  id: trace_001
  referenced_at: "2026-05-29T12:00:00Z"
  circle_version_at_reference: circle_v0.2
  reference_type: retrieval_reference
```

This helps clarify what rules applied at the time of AI reference.

Recommended principle:

> Trace events should record the active circle version at the time of reference.

This prevents future ambiguity.

---

## 16. Relationship to Royalty OS Visibility

Royalty-readiness previews may depend on trace and version history.

For example:

```yaml
royalty_visibility:
  allocation_readiness: review_required
  relevant_circle_versions:
    - circle_v0.1
    - circle_v0.2
```

If visibility, trace, or No-Inference settings changed over time, allocation-readiness review may need to consider those changes.

Circle Versioning helps separate:

```text
what was visible then
vs.
what is visible now
```

This distinction is essential for fair review.

---

## 17. Version History Display

A platform may display version history in a simplified form.

Reader-facing display:

```text
Meaning Structure Version: v0.3
Last updated: 2026-05-29
```

Creator-facing display:

```text
Circle Version History

v0.1 - Initial friction recorded
v0.2 - Core question refined
v0.3 - Deep Layer set to private and No-Inference Policy enabled
```

Reader-facing history should not expose private details.

Creator-facing history may show full change information.

---

## 18. Reversibility

Creators should be able to revise settings.

However, some changes may require careful handling.

Examples:

* making a public field private
* disabling AI training permission
* adding No-Inference protections
* changing royalty visibility
* archiving a circle version

Recommended approach:

```text
Allow future changes.
Preserve past records.
Do not rewrite trace history silently.
```

If a creator restricts a field after it was previously public, the system should respect the new boundary going forward while preserving historical accountability.

---

## 19. Version Conflict Handling

Conflicts may occur.

Examples:

```text
A trace event refers to circle_v0.1.
The creator later restricts the field in circle_v0.2.

A royalty preview depends on a trace created before No-Inference was enabled.

An AI system cached a summary from an older version.

A creator disputes an interpretation based on a superseded version.
```

Recommended handling:

```text
Record the active version at the time of the event.
Use the most restrictive current rule for future access.
Preserve historical trace for audit.
Do not expose private content from superseded versions.
```

---

## 20. Example Full Circle Version Object

```yaml
circle:
  id: circle_001
  current_version: circle_v0.3

circle_versions:
  - id: circle_v0.1
    previous_version: null
    created_at: "2026-05-28T00:00:00Z"
    status: superseded
    change_type:
      - initial_record
    summary: "Initial unresolved friction recorded."
    visibility_protocol:
      core_question: private
      initial_friction: private
      deep_layer: private
    no_inference_policy:
      enabled: false

  - id: circle_v0.2
    previous_version: circle_v0.1
    created_at: "2026-05-29T00:00:00Z"
    status: superseded
    change_type:
      - question_refinement
      - visibility_update
    summary: "Core question made public. Initial friction changed to friction-only."
    visibility_protocol:
      core_question: public
      initial_friction: friction_only
      deep_layer: private
    no_inference_policy:
      enabled: false

  - id: circle_v0.3
    previous_version: circle_v0.2
    created_at: "2026-05-30T00:00:00Z"
    status: active
    change_type:
      - no_inference_policy_update
      - meaning_boundary_update
    summary: "No-Inference Policy enabled and meaning boundary refined."
    visibility_protocol:
      core_question: public
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

---

## 21. Design Principles

### 21.1 Preserve Evolution

A creator's meaning structure should be allowed to change over time.

### 21.2 Preserve Accountability

Changes should be traceable.

### 21.3 Do Not Freeze Early Thought

Early versions should not permanently define the creator.

### 21.4 Do Not Rewrite History Silently

Past versions should remain available for audit where appropriate.

### 21.5 Protect Superseded Private Fields

Old versions should not expose private context after later restriction.

### 21.6 Record Active Version at Reference Time

Trace events should record which circle version was active when the reference occurred.

### 21.7 Separate Current Visibility from Historical Visibility

What is visible now may differ from what was visible then.

---

## 22. Non-Goals

Circle Versioning does not attempt to:

* replace Git version control
* define a final legal audit system
* determine copyright ownership
* determine royalty entitlement
* expose private historical context
* prevent creators from changing their views
* freeze a creator's early thought permanently
* rank creators by version activity
* prove authorship
* replace Trace Protocol
* define final dispute handling

This layer is a meaning-structure versioning model for creator-controlled AI-mediated platforms.

---

## 23. Summary

Circle Versioning records how a creator's meaning structure changes over time.

It tracks changes in:

```text
proto-friction
friction
questions
meaning boundaries
visibility settings
No-Inference Policies
trace policies
royalty visibility
```

Its central principle is:

> Meaning evolves.
> The system should remember the evolution without imprisoning the creator in the past.

Without Circle Versioning, Purity UI risks freezing a living thought.

With Circle Versioning, the creator's circle can change, mature, and remain accountable.
