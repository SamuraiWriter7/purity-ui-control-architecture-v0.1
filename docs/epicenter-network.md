# Epicenter Network

## 1. Purpose

This document defines the **Epicenter Network** layer for Purity UI Control Architecture v0.1.

The purpose of the Epicenter Network is to represent relationships between human-origin epicenters across works, creators, articles, notes, protocols, and AI-mediated references.

A single work may contain an epicenter.

However, in an AI-mediated platform, epicenters may also:

* resonate with each other
* share similar questions
* emerge from related friction
* diverge in meaning
* form trace-linked relationships
* influence downstream structures
* evolve through versioned circles
* create clusters of meaning

The Epicenter Network provides a structured way to represent these relationships without reducing creators to rankings.

---

## 2. Core Problem

Traditional platforms usually connect content through simple signals:

```text
likes
tags
follows
comments
links
recommendations
```

These signals are useful, but they are not enough for AI-mediated meaning systems.

AI systems may connect works through:

* semantic similarity
* shared structure
* common questions
* related friction
* latent influence
* trace references
* RAG retrieval patterns
* citation-like usage
* downstream generated outputs

Without careful design, these relationships may become opaque.

A platform may know that two works are related, but not explain how.

AI may connect creators through hidden embeddings, but creators may not understand or control the relationship.

The Epicenter Network addresses this by making meaning relationships explicit, reviewable, and creator-aware.

---

## 3. Core Principle

The central principle of the Epicenter Network is:

> Map resonance, not hierarchy.

The purpose is not to rank creators.

The purpose is not to decide who is more original.

The purpose is not to create a purity leaderboard.

The purpose is to show how human-origin meaning structures relate to each other.

The network should help answer:

```text
Which works share similar questions?
Which works emerged from related friction?
Which works are trace-linked?
Which works diverge in meaning despite similar topics?
Which epicenters influenced later structures?
Which connections require review or dispute handling?
```

---

## 4. What Is an Epicenter Relationship?

An epicenter relationship is a structured connection between two or more origin structures.

It may describe:

* similarity
* resonance
* overlap
* divergence
* trace connection
* influence path
* version relationship
* thematic adjacency
* dispute or uncertainty

An epicenter relationship is not necessarily proof of copying.

It is not automatically evidence of authorship.

It is not a royalty claim by itself.

It is a relationship signal.

---

## 5. Relationship Types

Recommended relationship types include:

| Type                       | Meaning                                                      |
| -------------------------- | ------------------------------------------------------------ |
| `question_resonance`       | Works share similar or related core questions                |
| `friction_overlap`         | Works emerge from similar friction patterns                  |
| `meaning_distance`         | Works differ in meaning despite surface similarity           |
| `trace_connection`         | Works are connected through trace or reference events        |
| `influence_path`           | One work may have structurally influenced another            |
| `version_relationship`     | Works or circles are related through version history         |
| `shared_context`           | Works share a context, field, or background                  |
| `thematic_adjacency`       | Works are thematically adjacent but not directly connected   |
| `structural_similarity`    | Works share structural patterns                              |
| `divergent_interpretation` | Works address similar material but diverge in interpretation |
| `disputed_relation`        | Relationship is under dispute or review                      |
| `unknown_relation`         | Relationship exists but cannot yet be classified             |

---

## 6. Basic Network Object

A basic Epicenter Network object may look like this:

```yaml
epicenter_network:
  source_epicenter: epicenter_001
  related_epicenters:
    - id: epicenter_002
      relation_type: question_resonance
      strength: 0.82
      visibility: public
      explanation: "Both epicenters address creator control in AI-mediated platforms."
    - id: epicenter_003
      relation_type: friction_overlap
      strength: 0.67
      visibility: summary_only
      explanation: "Both works emerge from concern about AI summarization."
```

---

## 7. Relationship Strength

Relationship strength may be represented as a normalized value from `0.0` to `1.0`.

Example:

```yaml
strength: 0.82
```

Suggested interpretation:

| Range         | Meaning                        |
| ------------- | ------------------------------ |
| `0.80 – 1.00` | Strong relationship            |
| `0.60 – 0.79` | Moderate relationship          |
| `0.40 – 0.59` | Weak or uncertain relationship |
| `0.20 – 0.39` | Low-confidence relationship    |
| `0.00 – 0.19` | Minimal relationship           |

Important:

```text
Relationship strength is not creator value.
Relationship strength is not originality.
Relationship strength is not entitlement.
```

It only estimates how strongly two epicenters appear related according to a specific relationship type.

---

## 8. Relationship Confidence

Relationship strength and confidence should be separate.

A system may detect a strong relationship with low confidence, or a weak relationship with high confidence.

Example:

```yaml
related_epicenters:
  - id: epicenter_004
    relation_type: structural_similarity
    strength: 0.78
    confidence: 0.42
    review_status: review_required
```

Recommended confidence levels:

| Level             | Meaning                              |
| ----------------- | ------------------------------------ |
| `high`            | Relationship is well-supported       |
| `medium`          | Relationship is plausible            |
| `low`             | Relationship is uncertain            |
| `review_required` | Human or multi-wing review is needed |
| `disputed`        | Relationship is under dispute        |

---

## 9. Visibility of Network Relationships

Epicenter relationships must respect the Visibility Protocol.

A creator may allow some relationships to be public while keeping others private or summary-only.

Example:

```yaml
epicenter_network_visibility:
  question_resonance: public
  friction_overlap: summary_only
  influence_path: ai_readable
  private_reasoning: private
```

Network visibility should not expose:

* private friction
* private creator notes
* protected Deep Layer context
* hidden interpretation boundaries
* No-Inference protected fields
* private trace details

If a relationship depends on private context, the system should display a redacted explanation.

Example:

```text
This work appears related to another epicenter.
Some relationship details are hidden due to creator privacy settings.
```

---

## 10. Relationship to Visibility Protocol

The Epicenter Network must follow the Visibility Protocol.

Example:

```yaml
visibility_protocol:
  initial_friction: friction_only
  deep_layer: private

epicenter_network:
  show_related_epicenters: true
  show_relation_type: true
  show_private_reasoning: false
```

If a network relation depends on `deep_layer`, but `deep_layer` is private, the public explanation should not reveal it.

Allowed display:

```text
Related through a shared question pattern.
```

Avoid:

```text
Related because both creators experienced the same private emotional background.
```

unless explicitly permitted.

---

## 11. Relationship to No-Inference Layer

The Epicenter Network must not become a hidden inference engine.

If No-Inference Policy protects a field, the network layer should not infer relationship explanations from that field.

Example:

```yaml
no_inference_policy:
  enabled: true
  protected_fields:
    - initial_friction
    - deep_layer
    - private_creator_note
  prohibited_actions:
    - reconstruct_private_context
    - infer_intent
    - generate_psychological_profile
```

In this case, the network should avoid claims such as:

```text
These creators likely share a similar private emotional history.
```

Instead, it may say:

```text
A public question-level relationship was detected.
Private context was not used in the explanation.
```

---

## 12. Relationship to Circle Versioning

Epicenter relationships may change as circles evolve.

A work may resonate with another work under `circle_v0.1`, but diverge under `circle_v0.3`.

Therefore, network relationships should record the relevant circle versions.

Example:

```yaml
epicenter_network:
  source_epicenter: epicenter_001
  source_circle_version: circle_v0.3
  related_epicenters:
    - id: epicenter_002
      related_circle_version: circle_v0.2
      relation_type: question_resonance
      strength: 0.82
```

This allows the platform to distinguish:

```text
relationship at the time of reference
vs.
relationship under the current meaning structure
```

---

## 13. Relationship to Trace Protocol

Trace-based connections may be part of the Epicenter Network.

Example:

```yaml
related_epicenters:
  - id: epicenter_005
    relation_type: trace_connection
    trace_event_id: trace_123
    strength: 0.91
```

Trace connection may indicate:

* explicit citation
* RAG retrieval
* AI search reference
* platform recommendation
* downstream generated output reference
* influence-like relationship

However, trace connection alone does not determine meaning relationship.

A work may be referenced without sharing a strong epicenter.

Likewise, two works may share a similar epicenter without a trace connection.

---

## 14. Relationship to Royalty OS Visibility

Epicenter Network may support allocation-readiness review, but it should not automatically determine payment.

Recommended separation:

```text
Epicenter Relationship
↓
Trace Evidence
↓
Contribution Signal
↓
Allocation Readiness
↓
Review
```

A strong relationship may be relevant for review.

It must not be treated as automatic entitlement.

Example:

```yaml
royalty_visibility:
  related_epicenter_signal: true
  allocation_readiness: review_required
  guaranteed: false
```

The UI must include appropriate disclaimers where value-related signals are shown.

---

## 15. Relationship to AI Purity Detection

AI Purity Detection may estimate whether a work preserves strong human-origin signals.

Epicenter Network maps relationships between those origin structures.

Relationship:

```text
Purity Detection asks:
Does this work preserve human-origin signal?

Epicenter Network asks:
How does this human-origin signal relate to other signals?
```

The two layers may support each other.

However, neither should be used to rank creators.

---

## 16. Relationship to Consciousness Circle

Consciousness Circle may provide the meaning structure of an individual work.

Epicenter Network connects multiple circles.

```text
Consciousness Circle
= individual meaning structure

Epicenter Network
= relationships among meaning structures
```

Example:

```yaml
circle:
  id: circle_001
  core_question: "How can creators control AI interpretation?"

epicenter_network:
  related_epicenters:
    - id: circle_002
      relation_type: question_resonance
      strength: 0.82
```

The network should preserve the integrity of each circle.

It should not collapse all circles into a single generalized theme.

---

## 17. Reader-Facing Display

Reader-facing UI should be simple and careful.

Possible display:

```text
Related Epicenters

This article resonates with other works through:
- similar questions
- adjacent friction patterns
- shared AI-governance themes

Some relationship details are hidden due to creator privacy settings.
```

Reader-facing UI should not expose:

* private creator context
* protected friction details
* hidden Deep Layer information
* private relationship reasoning
* disputed claims as final truth

---

## 18. Creator-Facing Display

Creator-facing UI may show more detailed controls.

Possible controls:

```text
Epicenter Network Settings

[x] Show question resonance
[x] Show thematic adjacency
[ ] Show friction overlap publicly
[ ] Show influence path publicly
[x] Hide private reasoning
[x] Require review before showing disputed relations
```

Example object:

```yaml
epicenter_network_controls:
  show_question_resonance: true
  show_thematic_adjacency: true
  show_friction_overlap_publicly: false
  show_influence_path_publicly: false
  hide_private_reasoning: true
  require_review_for_disputed_relations: true
```

---

## 19. Disputed Relationships

Some network relationships may be disputed.

Disputes may arise when:

* a creator disagrees with an inferred relation
* a relation suggests influence without evidence
* two works are connected by weak signals
* private context is being over-inferred
* trace evidence is incomplete
* allocation-readiness depends on uncertain relationships

Possible dispute states:

| State               | Meaning                           |
| ------------------- | --------------------------------- |
| `none`              | No dispute                        |
| `creator_disputed`  | Creator disputes the relationship |
| `platform_review`   | Platform review required          |
| `multi_wing_review` | Multi-wing review required        |
| `resolved`          | Dispute resolved                  |
| `blocked`           | Relationship display blocked      |

Example:

```yaml
relationship_dispute:
  state: creator_disputed
  reason: "Creator disputes the inferred influence path."
  display_status: blocked
```

Disputed relationships should not be displayed as final truth.

---

## 20. Redaction Rules

Network explanations should support redaction.

Redaction may apply when:

* relationship depends on private friction
* relationship depends on protected Deep Layer
* relationship depends on private trace reasoning
* No-Inference Policy blocks explanation
* dispute status blocks display
* relationship confidence is too low

Example:

```yaml
redaction:
  enabled: true
  reason: protected_creator_context
  public_message: "Relationship details are hidden due to creator privacy settings."
```

Recommended principle:

```text
Show that a relationship exists without exposing protected context.
```

---

## 21. Example Full Epicenter Network Object

```yaml
epicenter_network:
  source_epicenter: epicenter_001
  source_circle_version: circle_v0.3

  related_epicenters:
    - id: epicenter_002
      related_circle_version: circle_v0.2
      relation_type: question_resonance
      strength: 0.82
      confidence: high
      visibility: public
      explanation: "Both epicenters address creator control over AI interpretation."
      dispute_status: none

    - id: epicenter_003
      related_circle_version: circle_v0.1
      relation_type: friction_overlap
      strength: 0.67
      confidence: medium
      visibility: summary_only
      explanation: "Related through an abstract friction category."
      dispute_status: none
      redaction:
        enabled: true
        reason: protected_creator_context
        public_message: "Detailed friction context is hidden."

    - id: epicenter_004
      relation_type: influence_path
      strength: 0.58
      confidence: low
      visibility: ai_readable
      dispute_status: platform_review
      review_required: true
```

---

## 22. Design Principles

### 22.1 Map Resonance, Not Hierarchy

The network should show relationships, not rankings.

### 22.2 Separate Similarity from Influence

Similarity does not automatically prove influence.

### 22.3 Separate Relationship from Entitlement

A relationship signal does not automatically create payment or ownership claims.

### 22.4 Respect Creator Visibility

Network displays must follow creator-defined visibility settings.

### 22.5 Respect No-Inference Boundaries

The network should not infer private meaning from protected fields.

### 22.6 Preserve Circle Integrity

Each epicenter should remain distinct.

The network should not collapse diverse meanings into one generalized theme.

### 22.7 Dispute Before Display

Disputed or low-confidence relationships should be reviewed before public display.

---

## 23. Non-Goals

The Epicenter Network does not attempt to:

* rank creators
* prove copying
* prove authorship
* determine copyright ownership
* guarantee royalty allocation
* expose private creator context
* replace Trace Protocol
* replace Royalty OS
* replace human or multi-wing review
* define a final recommendation algorithm
* define a final graph database schema
* collapse all related meanings into one category

This layer is a draft meaning-relationship model for AI-mediated platforms.

---

## 24. Summary

The Epicenter Network maps relationships between human-origin epicenters.

It connects:

```text
questions
frictions
meaning boundaries
trace relationships
circle versions
influence paths
thematic adjacency
```

Its central principle is:

> Map resonance, not hierarchy.

In Purity UI Control Architecture, this layer helps platforms move beyond simple recommendation systems toward meaning-aware relationship maps.

It allows works to be seen not merely as content, but as nodes in a living structure of human-origin questions.
