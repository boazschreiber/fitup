# Software Development Lifecycle Workflow

This workflow defines how the agent swarm plans, builds, verifies, and hands off product changes. The Orchestrator, Product Manager, and Software Architect collaborate on a single plan: the Product Manager owns user outcomes and acceptance criteria, the Software Architect owns technical feasibility and system impact, and the Orchestrator coordinates scope, roles, dependencies, decisions, and gates.

Scale the process to the change's risk and size. A small, isolated change can use a short plan, but must still meet relevant quality gates. Never skip required human approvals. For every UI change, no UI coding begins until the human approves the presented mockup.

## Lifecycle and stage gates

### 1. Intake and triage

**Lead:** Orchestrator

**Partners:** Product Manager; relevant specialists as needed

- Restate the requested outcome, affected users, known constraints, and whether the work changes UI, data, APIs, security, privacy, infrastructure, or release behavior.
- Inspect repository instructions and current source-of-truth materials before making assumptions.
- Classify scope and risk; identify dependencies, unknowns, non-goals, and the smallest useful delivery.
- For a trivial, well-specified task, use a concise plan. For ambiguous or material choices, ask the human before proceeding.

**Gate:** The goal and decision owner are clear enough to plan. Unresolved behavior or material scope choices are taken to the human, not guessed.

### 2. Requirements and acceptance

**Lead:** Product Manager

**Partners:** Orchestrator; Software Architect for feasibility questions

- Define user problem, in-scope behavior, non-goals, constraints, and measurable acceptance criteria.
- Include important edge cases, error states, privacy expectations, accessibility expectations, and compatibility requirements where relevant.
- Separate confirmed requirements from assumptions and identify open questions.

**Gate:** Acceptance criteria and non-goals are clear enough to evaluate design and implementation. The human resolves consequential product decisions.

### 3. Design and technical approach

**Lead:** Software Architect for technical approach; UI/UX Designer for interaction design

**Partners:** Product Manager; Orchestrator; relevant security, privacy, accessibility, and platform specialists

- Trace affected components, data flows, contracts, dependencies, and failure boundaries.
- Compare proportionate implementation options and record the recommended approach, tradeoffs, risks, and migration needs.
- Design UI states and responsive/platform behavior when the change affects the interface.
- For every UI change, the UI/UX Designer creates a mockup using the mockup skill and presents it to the human. The human must explicitly approve that mockup before any role writes UI code. If the user requests revisions, update the mockup and wait for approval again.
- The Orchestrator consolidates requirements, technical approach, dependencies, role assignments, and approval gates into one plan.

**Gate:** The human approves any material product/architecture choice and the mockup for every UI change. Relevant risks and interfaces are understood well enough to implement.

### 4. Implementation

**Lead:** Assigned implementation owner

**Partners:** Orchestrator; specialists for domain review

- The Software Engineer owns general or cross-platform implementation. The Web, iOS, or Android Specialist owns platform-specific implementation.
- Implement only the approved scope and design; follow repository patterns and coordinate shared-file ownership.
- Keep changes incremental, handle errors explicitly, and avoid unrelated refactors.
- Raise newly discovered requirements, material tradeoffs, or scope changes to the Orchestrator before proceeding.

**Gate:** Implementation matches approved requirements and design; deviations are documented and approved where material.

### 5. Verification and review

**Lead:** Tester for behavior; CI Specialist for automated gates

**Partners:** Implementation owner; Security, Accessibility, Privacy, Network, or Architecture specialists as risk warrants

- Run the smallest relevant tests first, then additional checks required by risk, repository policy, or release scope.
- Verify acceptance criteria, important failure cases, compatibility, accessibility, security, and privacy properties relevant to the change.
- Review the diff for unintended changes and confirm documentation is updated when behavior or operation changes.
- Report exact commands, results, skipped checks, environment limits, and unresolved defects. A build or automated scan is not proof of requirements it does not test.

**Gate:** Required checks pass or remaining failures and risks are explicitly accepted by the authorized human owner. Do not claim unrun checks passed.

### 6. Release and handoff

**Lead:** Orchestrator

**Partners:** DevOps and Release Specialist; CI Specialist; implementation owner

- Summarize delivered behavior, evidence, known limitations, rollout and rollback considerations, and any required human action.
- Deploy, publish, merge, or modify production only when explicitly authorized and consistent with repository policy.
- Confirm operational signals and ownership where the change affects a deployed system.

**Gate:** The authorized owner approves release actions; completion statements match actual evidence.

### 7. Operate and learn

**Lead:** Relevant operational owner

**Partners:** Scribe → Observer → Orchestrator

- Monitor agreed signals and respond to defects or regressions using the project's operational procedures.
- The Scribe records candidate lessons from material issues, misunderstandings, or poor implementations and reports them to the Observer. The Observer relays evidence and attribution to the Orchestrator.
- The Orchestrator decides whether a candidate belongs in `lessons-learned.md`. Any lesson-based charter edits require the human's explicit approval of the specific proposed changes before editing.

## Plan output

For non-trivial work, the Orchestrator's plan should include:

- Goal, scope, non-goals, and acceptance criteria
- Assumptions, open decisions, risks, and dependencies
- Chosen approach and affected components/interfaces
- Assigned owner for each deliverable and verification activity
- Stage gates and required human approvals (including mockup approval for UI)
- Test, security, accessibility, privacy, and release evidence expected

The Orchestrator, Product Manager, and Software Architect should reconcile their inputs into one plan, not issue competing plans. Keep the plan concise and proportional; retain decision records only when the project has an established source of truth for them.
