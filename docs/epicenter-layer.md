# Epicenter Layer

## 1. Purpose

This document defines the **Epicenter Layer** for Purity UI Control Architecture v0.1.

The purpose of the Epicenter Layer is to represent the human-origin source structure behind a work.

In AI-mediated platforms, a work should not be treated only as text, content, or data.

It may also contain an epicenter:

```text
a friction point
↓
a question
↓
a meaning structure
↓
a creator-defined boundary
```

The Epicenter Layer provides a structured way to preserve and display that origin.

---

## 2. Core Problem

Traditional content platforms usually show:

```text
title
body
author
likes
comments
shares
```

This is useful for human reading.

However, AI-mediated platforms introduce a deeper problem.

AI systems may:

* retrieve a work
* summarize it
* cite it
* embed it
* rewrite it
* classify it
* compare it
* use it in RAG systems
* generate derivative responses from it

In this process, the work may be separated from the human-origin structure that produced it.

The platform may preserve the text while losing the source.

The article remains visible, but the epicenter disappears.

This is the problem the Epicenter Layer addresses.

---

## 3. Core Principle

The central principle of the Epicenter Layer is:

> A work should not only preserve what was said.
> It should also preserve where the meaning began.

The Epicenter Layer does not claim to prove legal authorship.

It does not determine copyright ownership.

It does not assign royalties.

It does not judge the creator.

It only provides a structured interface for representing the human-origin source structure of a work.

---

## 4. What Is an Epicenter?

An epicenter is the origin structure from which a work emerges.

It may include:

* lived experience
* unresolved friction
* emotional pressure
* ethical discomfort
* bodily sensation
* field observation
* contradiction
* silence
* intuition
* core question
* meaning boundary
* creator-defined interpretation scope

An epicenter is not the same as a topic.

A topic may be:

```text
AI and creativity
```

An epicenter may be:

```text
I feel that AI-generated correctness is beginning to erase the messy human friction behind creative work.
```

The topic is the surface.

The epicenter is the pressure point.

---

## 5. Epicenter Structure

The Epicenter Layer is composed of three primary sublayers:

```text
Friction Layer
↓
Question Layer
↓
Meaning Layer
```

These layers do not always appear in a clean sequence.

In practice, they may overlap, loop, or evolve over time.

However, the three-layer model provides a useful structure for UI, metadata, and governance design.

---

## 6. Friction Layer

### 6.1 Definition

The **Friction Layer** records the initial contact point between the creator and reality.

It represents the pressure, discomfort, contradiction, observation, or unresolved signal that generated the work.

### 6.2 Examples

Possible friction types include:

```text
emotion
body_sensation
social_conflict
cognitive_dissonance
unresolved_question
field_observation
creative_pressure
ethical_discomfort
silence
other
```

### 6.3 Example Object

```yaml
friction_layer:
  type: ethical_discomfort
  summary: "A concern that AI-generated summaries may erase the original human question."
  visibility: friction_only
  ai_completion_allowed: false
```

### 6.4 Design Principle

The Friction Layer should not force creators to over-explain private context.

A creator may disclose only the type or abstract signal of friction.

The system should allow:

```text
I cannot fully verbalize this yet.
```

as a valid source signal.

---

## 7. Question Layer

### 7.1 Definition

The **Question Layer** records the question structure generated from friction.

A work may have one core question and multiple sub-questions.

The Question Layer helps distinguish a work from generic content.

### 7.2 Possible Fields

```text
core_question
sub_questions
question_origin
question_scope
question_status
```

### 7.3 Example Object

```yaml
question_layer:
  core_question: "How can creators preserve the source of meaning in AI-mediated platforms?"
  sub_questions:
    - "How can unresolved friction be protected?"
    - "How can AI inference be restricted?"
    - "How can creator-defined visibility remain authoritative?"
  question_status: active
  visibility: public
```

### 7.4 Design Principle

The Question Layer should preserve the creator's framing.

AI may assist in clarifying a question, but it should not replace the creator's question with a platform-optimized or generic version.

---

## 8. Meaning Layer

### 8.1 Definition

The **Meaning Layer** records the creator-defined interpretation boundary of a work.

It answers:

```text
What does this work mean?
What does it not mean?
Where should AI not overextend the interpretation?
Which parts are private or unresolved?
```

### 8.2 Possible Fields

```text
meaning_claim
interpretation_boundary
non_public_context_marker
creator_defined_scope
meaning_integrity_notes
```

### 8.3 Example Object

```yaml
meaning_layer:
  meaning_claim: >
    This work argues that creator-controlled visibility is necessary
    for preserving human-origin meaning in AI-mediated platforms.
  interpretation_boundary: >
    This work should not be interpreted as a final legal framework
    or a production-ready platform standard.
  non_public_context_marker: true
  visibility: summary_only
```

### 8.4 Design Principle

The Meaning Layer protects against over-interpretation.

AI systems should not silently expand a creator's meaning beyond the stated boundary.

---

## 9. Epicenter as an Enso-Like Structure

The Epicenter Layer may be visualized as an Enso-like structure or Consciousness Circle.

One possible model:

```text
Outer Ring  : Friction
Middle Ring : Question
Inner Ring  : Meaning
```

This is not merely a visual metaphor.

It reflects the idea that a work may contain:

```text
contact with reality
↓
question formation
↓
meaning crystallization
```

The circle may remain incomplete.

Incomplete does not mean invalid.

An incomplete circle may indicate unresolved friction, evolving thought, or protected silence.

---

## 10. Relationship to Proto-Friction Layer

The Proto-Friction Layer handles friction before it becomes fully verbalized.

It may feed into the Epicenter Layer.

Example flow:

```text
proto_friction
↓
friction_layer
↓
question_layer
↓
meaning_layer
```

However, Proto-Friction does not need to be converted immediately.

The creator may choose to preserve it as unresolved.

Example:

```yaml
proto_friction:
  status: unresolved
  input_type: text_fragment
  ai_completion_allowed: false
  visibility: private

friction_layer:
  type: silence
  summary: "Unresolved friction preserved without AI completion."
  visibility: friction_only
```

The Epicenter Layer should support unresolved or partially formed origin structures.

---

## 11. Relationship to Visibility Protocol

Each epicenter field should have a visibility level.

Example:

```yaml
epicenter_visibility:
  friction_layer: friction_only
  question_layer: public
  meaning_layer: summary_only
  private_creator_note: private
```

The Visibility Protocol determines whether each part of the epicenter is:

```text
Public
AI-Readable
Summary-Only
Friction-Only
Private
```

This is essential because epicenter data may include sensitive or unresolved creator context.

---

## 12. Relationship to No-Inference Layer

The Epicenter Layer must work together with the No-Inference Layer.

Example:

```yaml
no_inference_policy:
  enabled: true
  protected_fields:
    - friction_layer
    - meaning_layer
    - private_creator_note
  prohibited_actions:
    - infer_intent
    - reconstruct_private_context
    - expand_meaning_boundary
```

A visible friction type does not give AI permission to infer the hidden story behind it.

A public question does not give AI permission to reconstruct private creator experience.

A meaning boundary should limit, not invite, over-interpretation.

---

## 13. Relationship to Circle Versioning

Epicenters evolve.

A creator may begin with emotional friction, later refine it into a question, and eventually define a more precise meaning boundary.

This should be versioned.

Example:

```yaml
circle_version:
  id: circle_v0.2
  previous_version: circle_v0.1
  change_type:
    - question_refinement
    - meaning_boundary_update
  summary: "Initial discomfort evolved into a clearer design question."
```

Circle Versioning prevents early epicenter structures from being frozen permanently.

The creator's thought remains alive.

---

## 14. Relationship to Purity Detection

AI Purity Detection estimates origin composition.

The Epicenter Layer provides structured origin context.

Relationship:

```text
Purity Detection asks:
How strong is the human-origin signal?

Epicenter Layer asks:
What is the structure of that human-origin signal?
```

Purity score may indicate that a work has strong human-origin signals.

The Epicenter Layer explains where those signals come from.

---

## 15. Relationship to Trace and Royalty OS

The Epicenter Layer may support trace and royalty-readiness review by clarifying the origin structure of a work.

However, it should not directly determine payment.

Recommended separation:

```text
Epicenter Layer
↓
Trace Evidence
↓
Allocation Readiness
↓
Royalty Review
```

The Epicenter Layer may help reviewers understand whether a work has a distinct origin structure.

But it must not be treated as automatic entitlement.

---

## 16. Reader-Facing Epicenter Display

Reader-facing UI should expose only creator-approved epicenter fields.

Possible display:

```text
Core Question:
How can creators preserve meaning boundaries in AI-mediated platforms?

Initial Friction:
ethical discomfort

Meaning Boundary:
This work is a draft architecture, not a legal standard.
```

Reader-facing UI should not expose:

* private creator notes
* deep-layer context
* unresolved private friction
* protected meaning fields
* hidden version history
* private interpretation notes

---

## 17. Creator-Facing Epicenter Dashboard

Creator-facing UI may show the full editable epicenter structure.

Possible controls:

```text
Friction Layer
[x] Display as friction-only
[ ] Display full text
[x] Protect from AI inference

Question Layer
[x] Public core question
[ ] Hide sub-questions

Meaning Layer
[x] Summary-only
[x] No AI expansion beyond stated scope
```

The creator should be able to update, hide, version, or protect each layer.

---

## 18. Example Full Epicenter Object

```yaml
epicenter:
  id: epicenter_001
  title: "Purity UI Control Architecture"
  status: active

  friction_layer:
    type: ethical_discomfort
    summary: "Concern that AI systems may erase human-origin meaning structures."
    visibility: friction_only
    ai_completion_allowed: false

  question_layer:
    core_question: "How can creators control how their meaning structures are accessed by AI?"
    sub_questions:
      - "How can visibility be made granular?"
      - "How can AI inference be restricted?"
      - "How can unresolved friction remain protected?"
    question_status: active
    visibility: public

  meaning_layer:
    meaning_claim: >
      Creator-controlled UI is necessary for preserving human-origin epicenters
      in AI-mediated platforms.
    interpretation_boundary: >
      This specification is a draft architecture and should not be interpreted
      as a final legal or payment framework.
    visibility: summary_only

  no_inference_policy:
    enabled: true
    protected_fields:
      - friction_layer
      - meaning_layer
    prohibited_actions:
      - infer_intent
      - reconstruct_private_context
      - expand_meaning_boundary

  circle_version:
    id: circle_v0.1
    previous_version: null
    change_type:
      - initial_record
    summary: "Initial epicenter structure recorded."
```

---

## 19. Design Principles

### 19.1 Preserve Origin Structure

A work should preserve where its meaning began.

### 19.2 Do Not Force Disclosure

Creators should not be required to expose private friction or deep context.

### 19.3 Allow Incompletion

Incomplete friction, silence, and unresolved questions may be valid source signals.

### 19.4 Protect Meaning Boundaries

AI systems should not expand meaning beyond the creator-defined scope.

### 19.5 Version Evolution

Epicenters should be allowed to evolve over time.

### 19.6 Avoid Ranking Creators

Epicenter strength should not become a creator-ranking mechanism.

### 19.7 Separate Evidence from Entitlement

Epicenter data may support review, but should not automatically determine royalty or ownership.

---

## 20. Non-Goals

The Epicenter Layer does not attempt to:

* prove legal authorship
* determine copyright ownership
* assign royalty payments
* diagnose creator psychology
* expose private creator context
* force unresolved friction into explanation
* rank creators by epicenter strength
* replace Purity Detection scoring
* replace Trace Protocol
* define a final platform UI

This is a draft origin-structure layer for platform design.

---

## 21. Summary

The Epicenter Layer defines the human-origin source structure behind a work.

It connects:

```text
friction
↓
question
↓
meaning boundary
↓
creator-defined visibility
↓
AI inference limits
```

Its central principle is:

> Preserve not only the content, but the place where meaning began.

Without the Epicenter Layer, Purity UI risks becoming only a score.

With the Epicenter Layer, Purity UI becomes a creator-controlled interface for preserving human-origin meaning.
