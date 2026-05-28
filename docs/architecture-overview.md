# Architecture Overview

## 1. Purpose

This document provides an architectural overview of **Purity UI Control Architecture v0.1**.

The purpose of this architecture is to define a creator-controlled interface layer for AI-mediated platforms.

It focuses on how platforms may preserve, display, and govern human-origin meaning structures such as:

* friction
* questions
* meaning boundaries
* disclosure settings
* AI inference permissions
* trace visibility
* royalty-readiness previews
* epicenter network relationships

This document explains how the main components of the architecture relate to each other.

---

## 2. Core Idea

Purity UI Control Architecture extends Purity beyond scoring.

A Purity score may estimate whether a work preserves a strong human-origin signal.

However, a score alone is not enough.

Creators also need control over:

* what is visible
* what remains private
* what AI may read
* what AI may summarize
* what AI must not infer
* whether trace logs are visible
* whether royalty-readiness previews are enabled
* how meaning structures evolve over time

The core idea is:

> Purity UI should not only display origin signals.
> It should give creators control over how those signals are accessed, interpreted, and circulated.

---

## 3. High-Level Architecture

The architecture consists of eight primary layers:

```text
Epicenter Layer
        ↓
Proto-Friction Layer
        ↓
Visibility Protocol
        ↓
Circle Versioning
        ↓
No-Inference Layer
        ↓
Royalty OS Visibility
        ↓
Epicenter Network
        ↓
Creator Control Dashboard
```

These layers do not always need to appear in this exact order in a user interface.

However, conceptually they form a pipeline:

```text
Human-origin friction
        ↓
Question formation
        ↓
Meaning boundary definition
        ↓
Creator-controlled disclosure
        ↓
AI access and inference control
        ↓
Trace visibility
        ↓
Value-circulation readiness
        ↓
Network-level meaning relationships
```

---

## 4. Layer 1: Epicenter Layer

The **Epicenter Layer** represents the source structure of a work.

It asks:

```text
Where did this work come from?
What friction generated it?
What question organized it?
What meaning boundary did the creator define?
```

The Epicenter Layer is composed of three conceptual sublayers:

```text
Friction Layer
Question Layer
Meaning Layer
```

### Friction Layer

The Friction Layer records the initial contact point between the creator and reality.

Examples include:

* emotion
* discomfort
* bodily sensation
* cognitive dissonance
* social conflict
* field observation
* ethical discomfort
* unresolved tension
* silence

### Question Layer

The Question Layer records the question structure generated from friction.

Examples include:

* core question
* sub-questions
* question origin
* question status
* question scope

### Meaning Layer

The Meaning Layer records how the creator defines the interpretive boundary of the work.

Examples include:

* meaning claim
* interpretation boundary
* creator-defined scope
* non-public context marker
* meaning integrity notes

The Epicenter Layer is the foundation of the architecture.

Without an epicenter, Purity UI becomes only a surface-level display.

---

## 5. Layer 2: Proto-Friction Layer

The **Proto-Friction Layer** preserves friction before it becomes fully verbalized.

This layer exists because meaningful human-origin signals are not always cleanly expressed as polished text.

Sometimes the first signal is:

* a fragment
* a vague discomfort
* a private note
* a body sensation
* an unresolved resistance
* a silence marker
* an unfinished intuition

The Proto-Friction Layer allows creators to preserve these signals without forcing premature completion.

Possible controls include:

```text
I cannot verbalize this yet
Save as unresolved friction
Do not allow AI completion
Keep as private creator-only note
Allow later conversion into core question
```

The principle is:

> Unfinished friction should not be forcibly completed by AI.

This layer is especially important because AI systems tend to complete ambiguity.

However, in creator-controlled meaning structures, ambiguity may need to remain protected.

---

## 6. Layer 3: Visibility Protocol

The **Visibility Protocol** defines who or what may access each part of the meaning structure.

A simple public/private switch is not sufficient for AI-mediated platforms.

Creators may need to specify different levels of access for:

* human readers
* platform AI
* external AI systems
* RAG pipelines
* search systems
* training systems
* royalty-readiness systems

The proposed visibility levels are:

| Level | Label         | Description                                                    |
| ----- | ------------- | -------------------------------------------------------------- |
| 1     | Public        | Visible to readers and AI systems                              |
| 2     | AI-Readable   | Hidden from public UI, readable by authorized AI systems       |
| 3     | Summary-Only  | Only a summary may be used by AI systems                       |
| 4     | Friction-Only | Only the friction category or abstract signal may be disclosed |
| 5     | Private       | Not visible to readers or AI systems                           |

Example:

```yaml
visibility_protocol:
  core_question: public
  initial_friction: friction_only
  deep_layer: private
  rotation_dynamics: summary_only
  trace_log: public
```

The principle is:

> Creator-defined visibility should be authoritative.

---

## 7. Layer 4: Circle Versioning

The **Circle Versioning** layer tracks changes in a creator's meaning structure over time.

A creator's question may evolve.

A friction point may become clearer.

A meaning boundary may shift.

A private layer may become public, or a public layer may later become restricted.

Without versioning, platforms may freeze a creator's early thought into a static identity.

Circle Versioning prevents this.

Example:

```yaml
circle_version:
  id: circle_v0.2
  previous_version: circle_v0.1
  change_type:
    - question_refinement
    - visibility_update
  summary: "The original emotional friction evolved into a design question."
```

Circle Versioning may track:

* friction changes
* question refinements
* visibility updates
* no-inference policy updates
* trace policy updates
* royalty visibility updates
* meaning boundary changes

The principle is:

> A creator's meaning structure should be allowed to evolve.

---

## 8. Layer 5: No-Inference Layer

The **No-Inference Layer** defines what AI systems must not infer, reconstruct, summarize, or expand.

This is one of the most important layers of the architecture.

AI systems often infer missing context.

In ordinary tasks, this may be useful.

However, when handling creator-defined meaning structures, silent inference can become dangerous.

Risks include:

* invented intention
* unauthorized interpretation
* private context reconstruction
* psychological overreach
* meaning boundary violation
* false attribution
* unauthorized summarization of protected fields

Possible controls include:

```text
Do not infer beyond this field
Do not reconstruct private context
Do not convert friction into psychological diagnosis
Do not summarize Deep Layer
Do not use this field for training
```

Example:

```yaml
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

The principle is:

> AI should assist within the boundary.
> AI should not silently expand the boundary.

---

## 9. Layer 6: Royalty OS Visibility

The **Royalty OS Visibility** layer shows trace-to-allocation-readiness information without claiming final payment.

This layer may display:

* trace events
* reference depth
* contribution score
* allocation-readiness status
* estimated preview
* review status
* dispute status

However, it must clearly separate:

```text
trace evidence
allocation-readiness preview
final payment execution
```

Example:

```yaml
royalty_visibility:
  trace_contribution_score: 4.1
  allocation_readiness: review_required
  estimated_preview:
    amount: 128
    currency: JPY
    guaranteed: false
  disclaimer_required: true
```

Required disclaimer:

```text
This preview is an estimation only.
It does not guarantee payment, ownership, entitlement, or final allocation.
```

The principle is:

> Trace and allocation readiness may be visible, but payment must not be implied as guaranteed.

---

## 10. Layer 7: Epicenter Network

The **Epicenter Network** layer maps relationships between human-origin epicenters.

A single work may contain an epicenter.

But in a larger platform ecosystem, multiple epicenters may resonate with each other.

They may share:

* similar questions
* overlapping friction
* related meaning structures
* trace connections
* influence paths
* version relationships
* thematic adjacency

Example:

```yaml
epicenter_network:
  related_epicenters:
    - id: epicenter_001
      relation_type: question_resonance
      strength: 0.82
    - id: epicenter_002
      relation_type: friction_overlap
      strength: 0.67
```

The purpose is not to rank creators.

The purpose is to map meaning relationships.

The principle is:

> Epicenter networks should reveal resonance, not create hierarchy.

---

## 11. Layer 8: Creator Control Dashboard

The **Creator Control Dashboard** is the practical interface where creators manage the system.

This dashboard may include controls for:

* core question visibility
* initial friction visibility
* deep layer privacy
* proto-friction capture
* trace visibility
* royalty-readiness preview
* AI training permission
* no-inference policy
* circle version history
* related epicenter visibility

Example:

```text
Creator Controls

[x] Core Question: public
[x] Initial Friction: friction-only
[ ] Deep Layer: private
[x] Allow Trace visibility
[x] Allow Royalty OS participation
[ ] Allow AI training use
[x] Enable No-Inference Policy
```

The dashboard is where the architecture becomes operational.

It converts abstract principles into actual choices.

The principle is:

> Creator control must be visible, actionable, and reversible.

---

## 12. System Flow

A typical platform flow may look like this:

```text
Creator writes or uploads a work
        ↓
Creator identifies friction, question, and meaning boundary
        ↓
Purity-related metadata is generated or declared
        ↓
Creator sets visibility levels
        ↓
Creator defines no-inference policy
        ↓
Platform displays reader-facing Purity UI
        ↓
AI systems access only permitted layers
        ↓
Trace logs record authorized references
        ↓
Royalty-readiness preview may be shown
        ↓
Epicenter relationships may be mapped
```

This flow is not mandatory.

It is one possible implementation pattern.

---

## 13. Reader-Facing vs Creator-Facing UI

The architecture should distinguish between reader-facing and creator-facing interfaces.

### Reader-Facing UI

Reader-facing UI may show:

* Purity badge
* public epicenter summary
* public core question
* public trace summary
* public royalty-readiness preview
* visible disclosure indicators

Reader-facing UI should not expose:

* private friction
* private creator notes
* Deep Layer content
* no-inference protected fields
* AI-only metadata unless authorized
* private version history

### Creator-Facing UI

Creator-facing UI may show:

* full epicenter structure
* proto-friction records
* visibility settings
* no-inference policies
* circle version history
* trace visibility controls
* royalty preview controls
* training permission controls
* relationship mapping options

The principle is:

> Transparency for readers should not become exposure of private creator context.

---

## 14. Relationship to Other Systems

### Relationship to AI Purity Detection Algorithm v0.2

AI Purity Detection estimates origin composition and review risk.

Purity UI Control governs how those signals are displayed and controlled.

```text
AI Purity Detection
        ↓
Purity UI Control
```

### Relationship to Consciousness Circle

Consciousness Circle provides meaning-origin structure.

Purity UI Control provides platform-level access and visibility controls for that structure.

```text
Consciousness Circle
        ↓
Visibility / No-Inference / Versioning
```

### Relationship to Trace Protocol

Trace Protocol records reference and reuse events.

Purity UI Control determines whether and how trace visibility appears in the interface.

```text
Trace Events
        ↓
Trace Visibility Controls
```

### Relationship to Royalty OS

Royalty OS may use trace and contribution signals for allocation-readiness review.

Purity UI Control may show preview-level information, but does not determine payment.

```text
Trace Evidence
        ↓
Allocation Readiness
        ↓
Royalty OS Visibility
```

---

## 15. Design Principles

### 15.1 Creator Sovereignty

Creators must retain authority over visibility, inference boundaries, and disclosure scope.

### 15.2 Privacy by Default

Private meaning structures should remain private unless explicitly disclosed.

### 15.3 AI Assistance Neutrality

AI assistance should not be treated as invalid by default.

The concern is not AI use itself, but whether AI-generated structure overwrites or obscures the human-origin epicenter.

### 15.4 No Silent Expansion

AI systems should not silently infer, reconstruct, or expand protected meaning fields.

### 15.5 Review Before Allocation

Trace or royalty-related UI should not imply automatic entitlement.

Review and dispute handling must remain separate from display.

### 15.6 Meaning Relationship, Not Ranking

Epicenter networks should map relationships, not produce creator hierarchy.

### 15.7 Reversibility

Creators should be able to update visibility, inference settings, and circle versions.

---

## 16. Non-Goals

This architecture does not attempt to:

* define a final production UI
* replace AI Purity Detection scoring
* determine legal authorship
* determine copyright ownership
* guarantee royalty payment
* rank creators by purity
* expose private creator context
* force creators to disclose deep meaning structures
* allow AI systems to infer beyond permitted boundaries
* define a final platform standard
* replace human or multi-wing review

This is a draft architecture for future platform design.

---

## 17. Summary

Purity UI Control Architecture v0.1 defines a creator-controlled interface layer for AI-mediated platforms.

It connects:

```text
human friction
↓
question formation
↓
meaning structure
↓
creator control
↓
AI-readable boundaries
↓
trace visibility
↓
value circulation
↓
epicenter network
```

Its core purpose is:

> Do not let human-origin meaning become invisible infrastructure.

Purity Detection measures origin signals.

Purity UI Control governs how those signals are displayed, accessed, interpreted, and circulated.
