# Proto-Friction Layer

## 1. Purpose

This document defines the **Proto-Friction Layer** for Purity UI Control Architecture v0.1.

The purpose of the Proto-Friction Layer is to preserve human-origin friction before it becomes fully verbalized, structured, or converted into a question.

In AI-mediated platforms, not all meaningful creator signals begin as polished text.

Some begin as:

* discomfort
* silence
* vague resistance
* bodily sensation
* unfinished intuition
* fragmented notes
* unresolved tension
* not-yet-formed questions

The Proto-Friction Layer protects these early signals from premature AI completion.

---

## 2. Core Problem

AI systems are good at completing patterns.

When given incomplete or ambiguous input, they often try to:

* summarize it
* clarify it
* complete it
* explain it
* diagnose it
* convert it into a polished question
* turn it into a structured argument
* produce a plausible narrative

This can be useful in ordinary writing assistance.

However, it can be harmful when the incomplete signal itself is the source.

A creator may not yet know what the friction means.

The friction may need to remain unresolved.

If AI completes it too early, the original human-origin signal may be overwritten.

The result may look clearer, but the source may become weaker.

---

## 3. Core Principle

The central principle of the Proto-Friction Layer is:

> Unfinished friction should not be forcibly completed by AI.

A platform should allow creators to preserve friction even when it is:

* vague
* incomplete
* fragmented
* private
* not yet verbalized
* not yet ready for interpretation
* not yet ready to become a question

This layer exists to protect the moment before language becomes structure.

---

## 4. What Is Proto-Friction?

Proto-friction is an early-stage human-origin signal that has not yet become a clear question, claim, or meaning structure.

It may appear as:

```text
Something feels wrong.
I cannot explain this yet.
There is discomfort here.
I feel resistance but do not know why.
This is not ready to become an article.
This is only a fragment.
This is silence, but it matters.
```

Proto-friction is not failure.

It is not noise.

It may be the earliest detectable form of a future epicenter.

---

## 5. Difference Between Friction and Proto-Friction

The difference is maturity of expression.

```text
Proto-Friction
= not yet verbalized or structured

Friction
= partially identified source pressure

Question
= structured inquiry generated from friction

Meaning
= interpretation or claim formed from the question
```

Example:

```text
Proto-Friction:
"I do not know why, but this AI summary feels wrong."

Friction:
"AI summaries may be erasing the original human discomfort behind the article."

Question:
"How can creators preserve the source of meaning in AI-mediated platforms?"

Meaning:
"Creator-controlled UI is necessary to protect human-origin epicenters."
```

The Proto-Friction Layer protects the first stage.

---

## 6. Valid Forms of Proto-Friction

Proto-friction may appear in multiple forms.

Possible input types include:

| Type                    | Description                                     |
| ----------------------- | ----------------------------------------------- |
| `text_fragment`         | Short unfinished text                           |
| `voice_note`            | Spoken but unstructured note                    |
| `handwritten_note`      | Handwritten fragment or mark                    |
| `image_note`            | Visual note, screenshot, diagram, or sketch     |
| `body_sensation_marker` | Non-verbal bodily signal                        |
| `silence_marker`        | Explicit record of meaningful silence           |
| `unresolved_question`   | Question that is not yet ready                  |
| `emotional_marker`      | Basic emotional signal without full explanation |
| `field_observation`     | Observation without interpretation              |
| `other`                 | Other creator-defined proto-friction form       |

---

## 7. Proto-Friction Object

A basic Proto-Friction object may look like this:

```yaml
proto_friction:
  id: proto_friction_001
  status: unresolved
  input_type: text_fragment
  content: "Something feels wrong about how AI summarizes this."
  ai_completion_allowed: false
  visibility: private
  created_at: "2026-05-28T00:00:00Z"
```

---

## 8. Status Values

Proto-friction may have different states.

Recommended status values:

| Status                  | Meaning                                                |
| ----------------------- | ------------------------------------------------------ |
| `unresolved`            | The creator has not yet interpreted the friction       |
| `partially_verbalized`  | The friction has begun to take verbal form             |
| `converted_to_friction` | The proto-friction has become a defined friction layer |
| `converted_to_question` | The proto-friction has become a core or sub-question   |
| `archived`              | The proto-friction is preserved but inactive           |
| `private_hold`          | The creator wants to preserve it without development   |
| `discarded`             | The creator has chosen not to preserve it further      |

Example:

```yaml
proto_friction:
  status: private_hold
  reason: "The creator wants to preserve the signal without interpretation."
```

---

## 9. AI Completion Control

The Proto-Friction Layer must include explicit control over AI completion.

Recommended field:

```yaml
ai_completion_allowed: false
```

When `ai_completion_allowed` is false, AI systems should not:

* complete the fragment
* explain the fragment
* summarize hidden meaning
* generate a likely backstory
* convert it into a polished claim
* turn it into a psychological diagnosis
* infer the creator's intent
* transform it into a final article structure

Possible values:

```yaml
ai_completion_allowed: false
ai_completion_allowed: true
ai_completion_allowed: creator_review_required
```

Recommended default:

```yaml
ai_completion_allowed: false
```

The safest default is to protect unfinished friction from automatic completion.

---

## 10. Visibility

Proto-friction should be private by default.

Recommended visibility levels:

| Visibility      | Meaning                                      |
| --------------- | -------------------------------------------- |
| `private`       | Not visible to readers or AI systems         |
| `friction_only` | Only abstract friction type may be disclosed |
| `summary_only`  | Only creator-approved summary may be used    |
| `ai_readable`   | AI may read under restrictions               |
| `public`        | Visible to readers and AI systems            |

Example:

```yaml
proto_friction:
  visibility: private
```

If exposed as friction-only:

```yaml
proto_friction:
  visibility: friction_only
  public_label: "unresolved discomfort"
```

Public display:

```text
Proto-Friction: unresolved discomfort
```

The underlying content remains hidden.

---

## 11. Relationship to Visibility Protocol

Proto-friction should be governed by the Visibility Protocol.

Example:

```yaml
visibility_protocol:
  proto_friction: private
  initial_friction: friction_only
  core_question: public
```

This means:

* proto-friction remains private
* initial friction may be shown only as a category
* core question may be public

The creator may later change visibility through Circle Versioning.

---

## 12. Relationship to No-Inference Layer

The Proto-Friction Layer must work closely with the No-Inference Layer.

Example:

```yaml
proto_friction:
  status: unresolved
  input_type: text_fragment
  ai_completion_allowed: false
  visibility: private

no_inference_policy:
  enabled: true
  protected_fields:
    - proto_friction
  prohibited_actions:
    - resolve_unfinished_friction
    - generate_backstory
    - infer_intent
    - reconstruct_private_context
```

This prevents AI from turning an unresolved fragment into a completed interpretation.

---

## 13. Relationship to Epicenter Layer

Proto-friction may later become part of the Epicenter Layer.

Possible flow:

```text
Proto-Friction
↓
Friction Layer
↓
Question Layer
↓
Meaning Layer
```

However, this conversion should not be automatic.

The creator should decide when or whether proto-friction becomes:

* defined friction
* a core question
* a sub-question
* a meaning claim
* an archived signal

Example conversion:

```yaml
proto_friction_conversion:
  from: proto_friction_001
  to: friction_layer
  conversion_type: creator_approved
  summary: "Unclear discomfort became ethical discomfort about AI summarization."
```

---

## 14. Relationship to Circle Versioning

Proto-friction may evolve over time.

Circle Versioning can record this evolution.

Example:

```yaml
circle_version:
  id: circle_v0.2
  previous_version: circle_v0.1
  change_type:
    - proto_friction_update
    - question_refinement
  summary: "The unresolved discomfort became a clearer question about AI-mediated meaning loss."
```

Versioning helps preserve the history of how a work emerged.

It also prevents the final article from erasing the earlier uncertainty that gave rise to it.

---

## 15. Relationship to Purity Detection

Proto-friction may support Purity Detection as an origin signal.

However, it should not be used as a simplistic score booster.

A proto-friction record may indicate:

* human-origin pressure
* lived uncertainty
* unresolved source signal
* early-stage meaning formation

But it should not automatically prove:

* authorship
* originality
* value
* royalty entitlement
* legal ownership

Recommended principle:

> Proto-friction is evidence of possible human-origin source pressure, not automatic proof of value.

---

## 16. Relationship to Trace and Royalty OS

Proto-friction should be handled carefully in trace or royalty systems.

Because proto-friction may be private or unresolved, it should not be exposed through:

* public trace logs
* royalty explanations
* allocation previews
* AI-generated summaries
* influence maps

unless explicitly permitted.

Example:

```yaml
royalty_visibility:
  show_proto_friction_details: false

trace_visibility:
  show_proto_friction_reference: false
```

If proto-friction contributes to review readiness, it should be described abstractly:

```text
Private origin signal present.
Details not disclosed.
```

---

## 17. Reader-Facing Display

Reader-facing UI should expose proto-friction only if the creator allows it.

Possible safe labels:

```text
Unresolved friction preserved
Private origin signal protected
Friction not yet verbalized
Creator has restricted AI completion
Proto-friction exists but is private
```

Avoid displaying:

* raw private fragments
* sensitive personal notes
* inferred backstory
* psychological explanations
* AI-generated interpretation of hidden friction

---

## 18. Creator-Facing Controls

Creator-facing UI may include controls such as:

```text
Proto-Friction Controls

[x] Save as unresolved friction
[x] Keep private
[x] Do not allow AI completion
[x] Do not infer intent
[ ] Convert to initial friction
[ ] Convert to core question
[ ] Archive this signal
```

Creator-facing dashboards should allow creators to preserve, update, convert, or discard proto-friction.

The system should not pressure the creator to complete it.

---

## 19. Example Full Proto-Friction Object

```yaml
proto_friction:
  id: proto_friction_001
  status: unresolved
  input_type: text_fragment
  content: "Something feels wrong about AI-generated summaries."
  public_label: "unresolved discomfort"
  visibility: private
  ai_completion_allowed: false
  created_at: "2026-05-28T00:00:00Z"
  updated_at: "2026-05-28T00:00:00Z"

no_inference_policy:
  enabled: true
  protected_fields:
    - proto_friction
  prohibited_actions:
    - resolve_unfinished_friction
    - generate_backstory
    - infer_intent
    - reconstruct_private_context
    - summarize_protected_fields
  enforcement_level: platform_required

conversion:
  status: not_converted
  allowed_targets:
    - friction_layer
    - question_layer
    - archive
  requires_creator_approval: true
```

---

## 20. Design Principles

### 20.1 Do Not Force Completion

Unresolved friction should not be forced into polished language.

### 20.2 Preserve Silence

Silence may be a valid origin signal.

### 20.3 Protect Ambiguity

Ambiguity may be meaningful and should not always be resolved.

### 20.4 Require Creator Approval

Conversion from proto-friction to friction, question, or meaning should require creator approval.

### 20.5 Private by Default

Proto-friction should remain private unless explicitly disclosed.

### 20.6 No Psychological Overreach

AI should not convert friction into diagnosis or personality profiling.

### 20.7 Allow Later Evolution

Proto-friction may evolve into a question or remain archived.

Both are valid.

---

## 21. Non-Goals

The Proto-Friction Layer does not attempt to:

* diagnose the creator
* interpret silence automatically
* force unresolved friction into language
* prove authorship
* determine copyright ownership
* determine royalty allocation
* expose private creator notes
* rank creators by emotional depth
* treat ambiguity as weakness
* replace the Epicenter Layer
* replace No-Inference controls
* make all friction visible to AI systems

This layer preserves early source signals without forcing premature structure.

---

## 22. Summary

The Proto-Friction Layer preserves the stage before friction becomes fully verbalized.

It protects:

```text
vague discomfort
silence
fragmented notes
bodily signals
unfinished intuition
unresolved resistance
not-yet-formed questions
```

Its central principle is:

> The first human-origin signal does not have to be complete to be real.

In Purity UI Control Architecture, this layer is essential because it prevents AI systems from erasing the earliest and most fragile form of human-origin meaning.

Without Proto-Friction, only polished thoughts survive.

With Proto-Friction, even the first tremor of meaning can be preserved.
