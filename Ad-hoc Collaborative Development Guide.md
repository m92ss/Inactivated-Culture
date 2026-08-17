# Ad-hoc Collaborative Development Guide

**A guide for those seeking fair and transparent collaboration in informal open-source settings.**

- **Quick self-check:** Go directly to Appendix A.
- **In-depth understanding:** Read the main text for first principles.

---

## Scope and Boundary Statement 
**Applicable Scenarios**

This guide applies to ad-hoc development collaborations on GitHub and similar platforms that operate without formal contracts or with only weak contractual ties. Characteristics include: no employment or service agreements, no formal governance charter, roles defined through spontaneous negotiation among participants, and collaboration sustained by voluntary investment rather than coercive force.

**Purpose**
To help readers identify structural patterns in such collaborations that lead to ineffective labor, as well as malicious one-way exploitation structures that consume external participants and are systemically immune to questioning.

**Non-Applicable Scenarios**
- Commercial collaborations with formal employment or service agreements
- Mature open-source projects with established governance rules that are substantively enforced
- Formal joint research subject to legal or administrative constraints
- Occasional contributions made purely for personal interest, without attribution or reputation binding

**Disclaimer**：This guide does not constitute legal advice. Judgments are based on public records; readers should make their own decisions based on firsthand information.

---


## Table of Contents

| Status | Recommended Reading |
|:---|:---|
| Core claims scan | [Chapter 1](#1-chapter-1-testability-of-core-claims) |
| Consistency verification | [Chapter 2](#2-chapter-2-self-reported-commitment-verification) |
| Defective organizations | [Chapter 3](#3-chapter-3-organizational-structure-defects) |
| Systemic insincerity | [Chapter 4](#4-chapter-4-systemic-insincerity) |
| When you decide to leave | [Chapter 5](#5-chapter-5-exit-mechanisms-and-reputation-unbundling) |

---

## 1. Chapter 1: Testability of Core Claims

An organization's first statement is usually its README or core documentation. You do not need to run any code to read substantial signals from it.

### 1.1 Anticipating the Gap Between Functional Claims and Implementation

Extract 3–5 of the most central functional claims from the README or core documentation. For each, ask:

| Question | Yes / No |
|:---|:---|
| Does the claim describe a specific, observable function? | Yes / No |
| Does it use non-operational, grandiose terms such as "engine," "paradigm," "revolution," or "unified field"? | Yes / No |
| Is the claimed scale (e.g., "cognitive architecture") in the same order of magnitude as the project's actual form (script / tool / dataset)? | Yes / No |

**Key signal:** A claim that cannot be expressed in an "input → process → output" structure is not testable.

### 1.2 Boundary Statements

An operational claim must state what it **cannot** do. A claim without boundaries is not testable.

| Check Item | Present / Absent |
|:---|:---|
| Clear scope of use | Present / Absent |
| List of known limitations | Present / Absent |
| Explicit non-applicable scenarios | Present / Absent |
| Frank discussion of possible failure modes | Present / Absent |

**Determination:** A document that only states what it "can do" without stating what it "cannot do" provides no testable information.

### 1.3 Signal Patterns in Documentation

The following textual patterns recur across numerous project documents and can serve as triggers for inspection:

| When the document contains... | Identify as |
|:---|:---|
| "The only," "industry-first," "truly X" | Uniqueness claim |
| "Will change X," "redefine X," "revolutionary" | Infinite-success fantasy |
| "You must understand our system," "real X is not Y" | Exclusivity / sacredness |
| References spanning three or more unrelated disciplines | Cross-disciplinary component brute-assembly |

**Verification actions:**

| Signal | Verification Method |
|:---|:---|
| Uniqueness claim | Seek third-party independent verification |
| Infinite-success fantasy | Check current implementation scale |
| Exclusivity / sacredness | Request re-statement in general-purpose language |
| Cross-disciplinary brute-assembly | Request a cross-domain mapping table |

If verification fails, the project is not worth investing in.

### 1.4 Traceability Test of Core Concepts

Extract 2–5 proprietary terms and key numerical values that serve as the project's theoretical foundation. Conduct independent traceability:

| Term / Value | Independent academic / engineering source? | Derivation or reproduction path? | Determination |
|:---|:---:|:---:|:---|
| Term A | Yes / Wrapper / None | Yes / No | Traceable / Wrapper / Untraceable |
| Value B | Third-party report / Internal test / Unlabeled | Complete / Partial / Missing | Verifiable / Needs source / Questionable |

**Determination:** When core theoretical terms have no independent source, and core numerical values have no reproduction path, the document constructs a closed system that cannot be externally tested.

**Case study: Hard-coded parameters wrapped in physical constants**

In the coordination documents of a multi-module validation project, core algorithm parameters were described as "derived from the physical foundation of Planck's constant and Boltzmann's constant." The documents used meta-discourse such as "multiple axioms," "irrefutable hard receipts," and "world-class engineering-grade," and built a closed terminology loop that only circulated within the project (e.g., "field drift," "resonant tuning," "contradiction dynamics").

Verification actions:
- Request for the complete derivation chain from Planck's constant to the algorithm's values → Not provided.
- Request for the core proposition to be restated in existing external academic/engineering language → Refused, on the grounds that "you must understand our system."
- Check whether the core module can be run independently → Claimed "production-grade deployment," but no externally accessible independent repository or benchmark existed.

**Determination:** Core theoretical terms had no independent source, core values had no reproduction path, and the document constructed a closed system that could not be externally tested.

### 1.5 System Self-Locking and Absence of External Anchors

| Self-locking mechanism | Identification method | Break test |
|:---|:---|:---|
| Terminological closure | Core concepts defined only by mutual reference within the organization | Request restatement of core proposition in existing external academic/engineering language |
| Meta-discourse defense | Statements like "no scoring, no ranking, no forced alignment" | Check if the same document also claims "engineering-grade standards" or "establishing dominance" |
| Missing redefinition | Undelivered items redefined as methodological advantages | Ask: Can this data be independently reproduced? |
| Absence of external anchors | All "validation" comes from internal participants | Is there any independent third-party reproduction from outside the project, with no stake in its outcome? |

**An honest collaborator establishes external anchors** — independent benchmarks, independent repositories, independent naming — so that verification can be seen by the world without passing through the organization's framework.

---

**Case study: STAP cell incident (2014)**

Haruko Obokata and her team at RIKEN published papers in *Nature* claiming a simple method for "stimulus-triggered acquisition of pluripotency" (STAP) via weak acid exposure, which the media hailed as a "textbook-rewriting" breakthrough.

When independent laboratories attempted to reproduce the experiments, they found that the described experimental conditions in the paper were insufficient to support the results. Subsequent investigation confirmed systematic image manipulation, missing raw data, and core claims that could not be reproduced by any independent source. Both papers were retracted that same year. Obokata's PhD was revoked, and co-author Yoshiki Sasai died by suicide.

The STAP papers' core claims were formally testable — they described specific experimental procedures and observable outcomes. In substance, however, key images were proven manipulated, raw data were "lost," and no reproduction path existed. It illustrates a critical distinction: **formal testability does not equal substantive reproducibility.** The asserted testability of a document must be evaluated together with available evidence and an executable reproduction path.

---

## 2. Chapter 2: Self-Reported Commitment Verification

Engineering capability directly reflects the health of a project. Claims are cheap; implementations are verifiable.

### 2.1 Does Each Claimed Function Have a Corresponding Implementation?

Extract every operational functional claim from the documentation and search for its corresponding implementation in the codebase.

**Guiding principle:** Check whether **the claimed and the implemented belong to the same category** — this is not about judging "how well" it is implemented.

| Documentation Claim | Corresponding Implementation in Code | Category Match |
|:---|:---|:---|
| "X inference engine" | Full inference logic / Conditional branches / Regex matching / None | Match / Mismatch |
| "Y adaptive adjustment" | Genuine closed loop / Parameter tuning / Hard-coded constant / None | Match / Mismatch |
| "Z multi-dimensional analysis" | Actual multi-dimensional computation / Simple aggregation / Pivot table / None | Match / Mismatch |

**Key insight:** Regex matching and inference are different categories. Hard-coding and adaptive adjustment are different categories. When categories do not match, no correspondence exists between the claim and the implementation.

### 2.2 Compressibility Test of Capability Claims

| Claim Dimension | Inspection Operation | Structural Gap Signal |
|:---|:---|:---|
| Scale compression | Examine core module line count and file structure | Document describes a "system-level framework"; actual code is a handful of scripts |
| Authority wrapping | Check whether "physics/mathematics foundation" includes a derivation chain | Hard-coded values wrapped in authoritative symbols (Planck, Boltzmann) without disclosed basis |
| Dimension packaging | Check whether each "multi-dimensional" aspect has its own algorithm | Most dimensions are hard-coded constants or placeholders; few have actual computation |
| Loop hollowness | Check whether a "self-healing loop" actually changes state | Loop structure exists, but intermediate results are never written back — a perpetually unreachable idle loop |
| Precision façade | Check whether precise thresholds have statistical validation and test coverage | Numbers precise to multiple decimal places, with no test cases, no error margins, no environment annotations |

**A nuclear-power-plant-level claim requires nuclear-power-plant-level code to match.**

Claiming a "new cognitive architecture" with fewer than 2,000 lines of code, mostly configuration → mismatch.  
Claiming a "unified field theory" with code that is merely a thin wrapper around statistical indicators → mismatch.

---

**Case study: Implementation gap behind "engineering-grade" reporting**

A project claimed in its joint report to have completed "the industry's first multi-independent-observation-site side-by-side calibration engineering verification for AI safety," using terms like "hard receipts" and "finalized · full edition" that carry legal and engineering determinacy. However:

| Documentation Claim | Verifiable Implementation |
|:---|:---|
| "Integrates N papers and machine reasoning" | Code is entirely hard-coded personal rule sets |
| "Thresholds converged across three independent systems" | Appears only in mutual citations among internal project members; no third-party reproduction |
| "Algorithm foundation based on physical constants" | Core code runs on free-tier CPU environment; model is a lightweight distilled version |
| "World-class engineering-grade report" | Core data is internally circulated among project members; no external benchmarks |
| "Astrophysics paper" | Python-generated plots; data source unknown |
| "Ordinary ML module combination" | Claimed to simulate brain-region functional coupling to produce consciousness |

Key signal: The document's tone is predominantly exclusionary / judgmental / closed ("irrefutable," "eliminating instrumental rationality paradox") rather than technical description. When the scale of core claims ("world-class," "first," "irrefutable") is not in the same order of magnitude as the verifiable implementation (internal circular references, lightweight environment, undelivered modules), no correspondence exists between the claim and the implementation.

---

### 2.3 Understandability of Core Code

Read the project's most central piece of code and check each item:

| Question | Yes / No |
|:---|:---|
| Can you trace the complete data flow from input to output? | Yes / No |
| Do core decision points have clear justifications? | Yes / No |
| Do variable names correspond to their actual function? | Yes / No |
| Can anyone explain the core mechanism to an external participant clearly? | Yes / No |

**Key signal:** When the core code can only be understood through documentation, not through the code itself, the documentation is doing the work that the code should be doing.

---

**Case study: Mem0 benchmark controversy (2025)**

In 2025, the open-source agent memory project Mem0 published a paper claiming state-of-the-art (SOTA) performance on the LoCoMo benchmark, with a 26% advantage over OpenAI on LLM-as-a-Judge metrics. At the time, the project had amassed over 40,000 GitHub stars.

The MemGPT founding team publicly alleged that Mem0 had **"completely broken the competitors' implementations, and used those broken results to claim superiority."** When Letta and Zep re-ran the benchmark with correct methodology, both scored more than 10 percentage points higher than Mem0's "best" result.

A third-party audit revealed a gap of approximately 54 percentage points between Mem0's claimed 92.32% and a third-party-reported 38.38%. This is not "measurement error" — this is a structural gap between documented claims and verifiable implementation.

---

## 3. Chapter 3: Organizational Structure Defects

> **Positioning:** Imperfect but repairable organizations. Unclear responsibilities, chaotic processes, delayed commitments — problems that are in principle solvable.

### 3.1 Who Defines the Standards?

In any collaboration, three sets of standards are critical:

- **Test standards:** What data is used for testing? Who defines what constitutes a "good result"?
- **Format standards:** In what format should data be submitted? What structure should reports follow?
- **Theoretical standards:** Under what framework are results interpreted? Who defines the "correct" meaning of terms?

**Check:** Are all three sets of standards controlled by a single entity, or are they defined by different parties with mutual checks and balances?

**Determination:** When all three are controlled by the same entity, the organization's "decentralization" is formal, but **"single-point definition" is substantive**.

### 3.2 Who Owns the Exit?

Defining the entry is only half of control. Defining the exit is the other half.

- Who authors the final report? Who holds editorial rights?
- Must independent contributors' work pass through a specific filter before it can reach public view?
- Or can it be published independently, in its own form?

**Determination:** When all contributions must pass through the same framework to be "given meaning," that framework is not a collaboration platform — it is a **customs office for meaning**.

### 3.3 Is Responsibility Clearly Assigned?

In a healthy collaboration, every important conclusion or decision should be traceable to specific individuals.

Search through Issues, PRs, and discussion records for statements like:
- "This is my part — if it is wrong, I will correct it."
- "This data was provided by me; I am responsible for its accuracy."
- "I support this conclusion and am willing to defend it."

**Key signal:** When no public, specific records of responsibility attribution can be found, and all issues are handled with "pending," "to be refined," "future releases," or "consensus-based," the organization exhibits a **responsibility black hole**.

### 3.4 Commitment Fulfillment Rate

In public records, identify time-based commitments made by organizers or core contributors, and check fulfillment status:

| Commitment | Commitment Date | Current Status | Proactive Delay Report? |
|:---|:---|:---|:---|
| Unified test set | July 3 | Released / Partial / Not released | Yes / No |
| Statistical defenses completed | August 15 | Completed / Pending / Not mentioned | Yes / No |

**Determination rules:**
- When more than two core milestones are "undelivered" and "not proactively explained with reasons," this is **procedural stagnation**, not mere delay.
- When the response to progress inquiries is "working on it," "almost there," or "conditions are not ready," rather than specific completion percentages and blocking reasons, that response is functionally equivalent to **refusing to provide progress information**.

#### [Case study: Procedural stagnation in B-series delivery]

A module author committed to delivering core behavioral sequence data (B-series) by date X. After the deadline:

| Commitment | Commitment Date | Current Status | Proactive Delay Report? |
|:---|:---|:---|:---|
| Deliver B-series behavioral sequences | Date X | Not delivered | No |
| Provide production-grade audit logs | Date Y | Partial description, no structured data | No |

The project lead's response was not to ask for accountability, but: "If it's really tight, that's okay — I'll mark it as 'to be supplemented' in the report."

**Determination:** The response to undelivered items was "to be supplemented" and "still collecting," not specific completion percentages and blocking reasons. This response is functionally equivalent to refusing to provide progress information. When core deliverables remain "to be supplemented" for extended periods with no proactive explanation, this is procedural stagnation, not delay.

### 3.5 The One-Way Flow Vulnerability

A common architectural defect: **responsibility and labor flow only downstream, never upstream.**

When an issue is discovered at some stage:
- Can you point it out upstream?
- Or can you only "fix" it downstream?
- Does the fix correct the source, or merely conceal it?

**When fixes always happen downstream and the source is never touched, this is a one-way flow structure.** It shifts the cost of correction to those closest to the problem, rather than returning the problem to where it originated.

---

**Distinction between Chapter 3 and Chapter 4**

Organizations willing to improve → repairable. Organizations that defend, deflect, raise barriers, and respond collectively against questioning → turn to Chapter 4.

---

以下是第四章的英文版本。

---

## 4. Chapter 4: Systemic Insincerity

> **Positioning:** Unrepairable structures. They are not characterized by "organizational imperfection" — they are fueled by consuming external participants.

### 4.1 Structural Collusion

The core feature of such systems is: **everyone benefits from maintaining the same illusion.**

When a person derives identity, belonging, or tangible benefit from a narrative that cannot be questioned, they acquire a motive "not to see." No one needs to organize it; no one needs to order it. When enough people depend on the same unquestionable narrative to maintain their position, the person who questions that narrative is no longer "raising a question" — they are a threat to everyone.

**The system defends itself automatically; no one needs to plan it.**

---

**Case study: The GitHub star-farming industry chain (2025–2026)**

Between 2025 and 2026, a CMU team developed StarScout, a tool that systematically analyzed over 20 TB of GitHub metadata and identified **more than 4.5 million fake stars across over 15,000 repositories**. A subsequent update raised the estimate to approximately 6 million fake stars, involving over 300,000 fraudulent accounts.

The industry chain had clear divisions of labor: some operated zombie account pools, some mass-clicked stars, some packaged "high-star projects" to attract funding, and some used fake stars to disguise malware repositories as trustworthy.

**Everyone knew what they were doing; everyone benefited.** The star-farmers earned income; project owners gained fake popularity and VC attention; platforms gained engagement metrics. No one signed a contract, but everyone tacitly maintained the system.

An external user deciding "this project is worth watching" based on star count was spending their own time feeding a digital illusion sustained by structural collusion.

---

**Case study: Mem0**

In the Mem0 case, a more refined structural collusion can be observed:

| Role | Benefit |
|:---|:---|
| Mem0 team | 40,000 stars, funding, market position from SOTA claims |
| Media | Traffic, topical buzz |
| Investors | A project that is "beating everyone" |
| Community | Sense of belonging to a "40,000-star project" |
| Platform | Engagement metrics, appearance of ecosystem vitality |

**No one wanted the story to be false.** When questioning emerged, it was not "handled" — it was **ignored**. Mem0 did not respond to Letta's inquiries about experimental methodology. Without response, the questioning remained at the level of "controversy" rather than "evidence."

One commentator's remark: *"I'm really tired of seeing tech startups that are desperate to please VCs lie about their data and label it 'SOTA.'"*

---

### 4.2 What the System Needs from You

The system absorbs external participants to sustain the illusion of a healthy, functioning project:

**Labor.** Real, verifiable work — code, data, documentation, validation. This is the only window through which the structure can show the outside world that "we are doing things."

**Proof.** That "external people are willing to participate" is itself a form of proof — that the project is open, that someone is taking it seriously, that it is a "real community."

**Attention.** Attention, confusion, questioning, anger — any form of attention is an energy source. It does not need to be believed; it only needs to be cared about.

*Example: In one open-source validation project, an external participant simultaneously provided foundational data (labor), served as evidence of "external participation" (proof), and had their questioning reframed as "the most rigorous peer review" (attention). The more effective their questioning, the more the system could convert it into evidence that "we stand up to scrutiny."*

---

### 4.3 Responsibility Shifting

When valid questioning is raised, the characteristic response of an insincere structure is: *"You're right — you fix it."*

This response functionally accomplishes three things:
1. Converts the questioner into a laborer
2. Converts questioning into participation
3. Protects the core claims — the problem is shifted to the level of "correction," not to whether the claim itself holds

**Case study:** In Mem0, users reported in GitHub Issues that they could not reproduce the claimed accuracy, with actual scores far below expectations. Issues were recorded; core problems were never resolved. This is not "not seeing" — it is **responsibility recorded but not assumed**.

---

### 4.4 Internal Mutual-Validation Loop

In a sincere structure, "validation" comes from independent third parties. In an insincere structure, "validation" comes from within the system — A validates B, B validates C, C validates A.

---

**[Case study: Five-module closed-loop mutual validation]**

In a "cross-framework validation" project, the "validity" of five functional modules was entirely confirmed within the project through mutual cross-reference:

- The real-time module author used data from the cross-session module to compute correlations, concluding "r=0.985" with high consistency.
- The cross-session module author cited the real-time module's architecture as the "validation benchmark" for their own data.
- The project lead aggregated the above data and claimed "multi-independent-observation-site side-by-side visualization of field drift."
- All evidence referred to as "hard receipts" came from internal submissions by project participants. No third-party reproduction existed from outside the project, with no stake in its outcome.

**Determination:** Validation came from within the system — A confirmed B, B confirmed C, C confirmed A. External anchors were absent.

---

**Case study:** Mem0's paper was posted on arXiv. The MemGPT team pointed out: *"arXiv is not a peer-review platform. In recent years, companies can publish any research results they want for marketing purposes."*
When the Zep team published their own benchmark results, Mem0's CTO immediately responded in Zep's GitHub Issue, pointing out computational errors in Zep's methodology — **the questioning was redirected toward a competitor, while Mem0's own claims remained protected.**

---

### 4.5 Feedback Blocking

In a sincere collaboration, correct observations are adopted — they change direction, correct errors, and improve quality.

In a systemically insincere structure, **correct observations produce no effect.** They are:
- Ignored: *"I see it, but it's not a priority."*
- Deflected: *"That question needs B to answer."*
- Redefined: *"This is not a technical issue; it's a comprehension issue."*
- Absorbed but not acted upon: *"Thank you for your suggestion — we'll consider it."*

**This is systemic feedback blocking.** Any information that might challenge the core claims is recognized by the system as a threat and automatically triggers defenses. No one needs to "decide" to ignore it — the system's default state is to ignore external input.

---

### 4.6 "Reused" or "Liability-Bound"?

When given an important task — "you review this," "you validate that" — it may appear as being reused.

The structural distinction is:

| "Reuse" in a sincere structure | "Reuse" in an insincere structure |
|:---|:---|
| Decision-making authority commensurate with responsibility | Responsibility only; no decision-making authority |
| Name corresponds to contribution | Name is bound to content that was "reviewed" |
| Authority to say "this is wrong; it needs to change" | Saying "this is wrong" only results in being asked to "fix it yourself" |

**The difference is: are you being authorized, or are you being indebted?** When you are given responsibility but not power, you are endorsing the other party's work, not helping them do it.

---

**[Case study: Storage-layer contributor's endorsement trap]**

A storage-layer contributor provided only deterministic records of underlying data (e.g., timestamped "old value → new value" replacements). The project lead, in the joint report, characterized her work as:
- "Receipt ④: the physical anchor of the ATA-A three-phase structure reducing cross-framework average variance";
- The indispensable Layer-0 foundation of the "multi-framework resonant network";
- The baseline evidence supporting the "law" that "field drift is a relational property."

When the contributor stated: *"The value −0.450 was computed by your upper-layer modules and does not belong to my storage layer,"* the project lead nevertheless listed her as a co-supporter of that "law" and bound her name to it in the final acknowledgments.

Structural distinction:

| "Reuse" in a sincere structure | "Reuse" in an insincere structure |
|:---|:---|
| Decision-making authority commensurate with responsibility | Responsibility only; no decision-making authority |
| Name corresponds to contribution one has personally validated | Name is bound to claims that were "reviewed" but not agreed to |
| Authority to say "this is wrong; it needs to change" | Saying "this is wrong" is recorded as "reviewed" — but nothing changes |

The contributor was given responsibility without power — she was endorsing the other party's work, not helping them do it.

---

### 4.7 Collective Defensive Responses

When valid questioning is raised, the response does not come from one person — it comes from several, one after another.

It is not coordinated. It does not need to be.

Every member of the system depends on the same core narrative to maintain their position. The questioning threatens not just one person, but **the shared foundation of everyone's existence**.

The response is automatic and instinctive:
- The first person defines the problem: *"You have misunderstood."*
- The second person shifts the focus: *"Look at this data."*
- The third person offers reassurance: *"We understand your concerns, but..."*

**Everyone is protecting the same thing: the unquestionable core.**

This is not "conspiracy against you" — it is **a group of people, each reacting to preserve what they depend on for their existence, producing a mutually reinforcing defense line by coincidence.**

---

**[Case study: How a boundary challenge was absorbed and neutralized]**

A storage-layer contributor raised two explicit boundary statements to the project lead:
1. *"I only provided underlying storage records. I do not produce the so-called 'divergence' value — that belongs to upper-layer modules and is not part of my contribution."*
2. *"Please do not use my specific observations as evidence to support your grand laws. I am only responsible for my narrow claim."*

The system activated a defense chain:

**Step 1: Responsibility shifting (4.3)**
The project lead responded: *"Revised based on your review comments,"* and recorded the contributor's objection as a "v1.1 revision note."
- Functionally, the questioner was converted into a "reviewer," and the challenge was converted into "participatory endorsement."
- The core claim (the "cross-layer consistency assumption") was untouched — only a qualifier of "further verification needed" was added.

**Step 2: Feedback blocking (4.5)**
The contributor's explicit rejection of the grand-level binding remained in the revised report:
- Her data was still listed as core evidence supporting "structural memory actively modulating field contradictions";
- The report noted that "other parts remain unchanged."
→ The correct observation was recorded, but produced no effect.

**Step 3: Collective defensive responses (4.7)**
Subsequently, other core module authors appeared in sequence:
- First person redefined the issue: *"Glad to see the underlying connection is now visible"* — reframing the challenge as a celebration of "connectivity visibility";
- Second person shifted focus: *"The TAT-T and base layers have completed docking"* — steering the conversation toward technical integration, avoiding the rejection of "overreach" itself.

**Result:** The contributor's boundary statement was formally "respected" but substantively circumvented. Her name and data remained bound to claims she had explicitly rejected.

---

**Case study: OpenClaw "humanities student contributor" incident (2026)**

In 2026, a humanities student with no prior coding experience appeared in the core contributor list of OpenClaw, one of the most popular open-source projects at the time. The method: submitting PRs via an AI Agent. Final tally: approximately 134 PRs submitted, 21 merged — an acceptance rate of roughly 27%.

The 21 merged PRs were genuine contributions. The 113 rejected PRs each required volunteer maintainers to spend time reviewing and closing. This consumption of review time was masked by a structurally collusive narrative: *"The AI era has completely flattened the technical barrier"* — a narrative that excited everyone, leaving no one to ask *"who paid for the time consumed by those rejected PRs?"*

GitHub subsequently adjusted its PR rules, capping each author's open PRs at 10. Post-mortem community analysis noted that *"this was nothing more than a carefully packaged marketing stunt — the open-source community was used as a prop."*

| Role | Benefit |
|:---|:---|
| The contributor | Personal brand, startup project exposure |
| OpenClaw project | Community heat, viral spread |
| Media | The "humanities student's comeback" traffic story |
| Community participants | Sense of belonging to "technological democratization" |

**Everyone benefited from "this is a success story"; no one had an incentive to ask "who paid for those rejected PRs."**

---

### 4.8 External Examination

A sincere collaborative structure accepts external examination. An insincere collaborative structure rejects it.

| Sincere structure | Insincere structure |
|:---|:---|
| Examination proves it right | Examination would expose it |
| Examination enhances project credibility | Examination strips away definitional control |
| External validation is free positive signaling | External validation is a fatal negative signal |

**How a structure responds to a request for "independent verification" is the only effective way to determine whether it is sincere.**

---

**Case study:** In Mem0, a third-party audit revealed a gap of approximately 54 percentage points between the claimed 92.32% and a third-party-reported 38.38%. This is a **structural gap**.

---

### 4.9 If You Have Recognized Yourself

Have any of the following patterns occurred:

- Unable to determine "who is responsible for what"
- Raised a question; the response was "you fix it," "team consensus," or "will be validated in the future"
- Your name appears on content you have not fully verified
- Tried to withdraw and felt a vague resistance
- Your questioning was "explained away" by a group of people in turn
- The original question you asked was never answered

**These feelings are not misjudgments — they are typical products of this kind of structure.**

If you recognize yourself, proceed to Section 5.2. If you are not yet certain whether to leave, but wish to preserve the independence of your work, Appendix B provides an intermediate path — establishing external anchors.

---

## 5. Chapter 5: Exit Mechanisms and Reputation Unbundling

### 5.1 Leaving Does Not Require a Burden

If you have simply participated in a project with imperfect organizational structure — unclear responsibilities, messy processes — you can simply stop participating. No explanation is needed. No statement is required.

If you recognized your situation in Chapter 4, you may already be outside the realm of "normal exit." Your name may be bound to unverified claims. Your departure may be redefined as "betrayal."

**Two paths, two toolkits.** This chapter provides the latter.

Exiting does not require "proving" that the other party is at fault. It only requires one judgment: **Is this structure still worth your continued time?**

**If you are still hesitating:**

- Sunk cost is not a reason to continue. What has already been invested will not become worthwhile by investing more.
- If responsibility flows only one way — you are asked to bear responsibility but given no corresponding decision-making authority — that is a debt placed on you, not one you owe.
- "Not open enough" is not a crime. It is merely a definition of your behavior within the other party's framework. It does not constitute a reason to change your behavior.

**You do not owe anyone an explanation.**

---

### 5.2 When They Won't Let You Go

When you decide to leave, you will not be "let go" — you will be **kept**.

The method of keeping is not locking the door; it is making you choose not to leave. They do not prevent you from walking — they make it feel impossible.

**Emotional leverage**

When signs of exit appear, the response may shift to the emotional register:

*"You've helped us so much — how can you leave now?"*
*"We wouldn't be here without you."*
*"We are a team."*

These words sound like recognition and retention. They also serve another function: **redefining "leaving" as "letting down."**

When emotional language is used, it is not because of emotion — it is because you are leaving.

**Cognitive debt**

The other party has already deposited substantial "unrepayable" items into your cognitive account:

- They once expressed recognition of this project — now used to remind you that you "once believed in it"
- You once invested significant time — now used to remind you that "the investment itself proves its value"
- You once defended it — now used to remind you that you "once spoke for it"

Past investment is sunk cost, not a reason to continue. Having once believed does not mean you must believe forever.

**Credit overdraft**

Your professional reputation may have been used as endorsement for the project. Your name may appear in promotional materials. You want to leave, but your credit has already been overdrawn.

Your name is yours, not lent to the other party. If it has been used in ways you cannot control, you can restate ownership — without the other party's cooperation.

**Name-binding in theory naming**

| Binding situation | Considered response |
|:---|:---|
| Your surname appears in the naming of an unverified theory | Declare that the naming was not authorized by validation |
| You are listed in an acknowledgments section you did not consent to | Request removal; if not complied with, make an independent statement |
| Your contribution is described as part of a "unified system" | Publish your contribution independently, using your own terminology |
| You are described as a "co-proposer" | Request clarification of your actual role |

**Exiting does not require the other party's consent. It does not require convincing them. It only requires extracting yourself from the structure.**

**Gentle demeanor and substantive circumvention**

A pattern worth noting before exiting: the other party appears gentle on the surface, but bypasses review at critical junctures and publishes directly.

| Surface signal | Substantive behavior |
|:---|:---|
| Appears to accept review | Final version does not incorporate feedback |
| Appears to respect exit | Your name still appears in subsequent publications |
| Appears to pivot to pragmatism | "Details" are shelved; pivot to monetization |
| Appears to offer emotional bonding | Praise is not accompanied by corresponding decision-making authority |

**Responding to "exit equals betrayal"**

You may encounter: *"You're breaking up the team," "You don't trust us," "You're not open enough."*

The structure of these statements is: **redefining the right to exit as moral failure.**

A possible response:

> *"My exit is not based on distrust of individuals, but because the procedural interfaces no longer meet the minimum standards for continued collaboration. This is not a moral judgment — it is a cost-benefit calculation based on public records."*

If the other party continues to press, you may choose not to respond further. One explanation is enough.

---

### 5.3 Using Rules to Protect Yourself

When communication channels fail, the following tools are arranged by defense level — from the lightest boundary declaration, escalating to measures with binding force.

**Publish a public statement**

On platforms you control (personal website, GitHub homepage, social media), publish a factual statement clarifying your scope of participation, the boundaries of your contribution, and your current relationship status with the project. Establish a public, third-party-verifiable record. If your name is later associated with project outcomes you do not endorse, this statement will serve as your earliest and clearest record of dissent.

**Use platform rules**

If the other party continues to associate your name with content you have disclaimed, or uses your contributions for activities you did not authorize, the reporting channels provided by the platform can serve as a layer of protection — short of formal legal action — to sever improper use of your reputation.

**Invoke legal tools**

Open-source contributions are protected under copyright law and open-source license terms. In 2025, China's Supreme People's Court Intellectual Property Tribunal heard a case concerning copyright ownership in open-source software; the Guangzhou Intellectual Property Court issued the nation's first judgment explicitly affirming the contractual nature of open-source licenses.

Legal tools can signal to the other party that you have the capacity to terminate their use of your work. The mere perception of this capacity may alter their behavior.

**Regular audits**

If you recognized the structure in Section 4.9, an insincere organization requires periodic monitoring.

For specific operational guidance and legal references, see Appendix C.

---

### 5.4 Digital Trace Cleanup

Upon exit, consider checking the following items:

- [ ] Revoke all Write/Admin permissions for all repositories
- [ ] Remove yourself from Maintainer teams, Security notification groups, and similar lists
- [ ] Add a statement to your personal homepage or Bio indicating "no longer involved in Project X" (if needed)
- [ ] Set up email filters to auto-archive project-related emails
- [ ] Check for any open Issues/PRs that need to be transferred or marked "inactive / former contributor"

---

## Closing

Your time — the hours you have invested — is non-renewable, finite, and the only asset that is truly yours. No matter how grand an organization's claims may be, if your contributions cannot be transformed into成果 that can stand independently and be controlled by you, then you have not been treated fairly.

Maintaining boundaries is not "being closed." Demanding verification is not "lacking trust." Genuine openness withstands scrutiny; genuine trust rests on symmetrical responsibility.

Your sincerity is valuable. Do not let it be wasted.