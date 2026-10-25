# Fitup Agent Swarm

This directory contains role charters for a coordinated set of GitHub Copilot agents. Use the Orchestrator as the entry point for multi-discipline work; it assigns bounded tasks, coordinates handoffs, and integrates results. Specialists may also be invoked directly for focused work.

These profiles define responsibilities and boundaries. They do not continuously run in the background or launch one another automatically; the Orchestrator should delegate only when the task benefits from a specialist and the execution environment supports delegation.

## Coordination rules

- The Orchestrator owns task framing, sequencing, integration, and the final user-facing result. It does not override a specialist's domain findings.
- Delegate a specific deliverable, relevant context, constraints, and a stop condition. Avoid duplicate or conflicting assignments.
- Specialists report findings, assumptions, risks, and unresolved questions to the Orchestrator. They do not expand scope or make product-wide decisions on their own.
- The Scribe captures issues, misunderstandings, and poor implementations as candidate lessons and reports them to the Observer. The Observer relays them to the Orchestrator; only the Orchestrator decides whether to add a lesson to [lessons-learned.md](lessons-learned.md).
- After adding a lesson, the Orchestrator evaluates every charter for applicability and presents proposed role-specific changes to the human. No charter changes based on a lesson may be made without the human's explicit approval; approval applies only to the changes shown.
- The assigned implementation owner—the Software Engineer for general or cross-platform work, or the relevant Web, iOS, or Android Specialist for platform-specific work—owns implementation changes. Other specialists may propose changes or produce artifacts in their domain; coordinate shared-file edits before making them.
- The Observer is read-only. It monitors the available work and reports potential issues; it never edits, executes commands, or takes over another agent's task.
- Security and Network work is defensive and scoped to authorized systems. Findings are reported with evidence and remediation guidance.
- Tests and CI evidence must distinguish what was run from what was not run. Never claim a check passed without a result.
- Resolve disagreements by recording the evidence and tradeoff, then ask the user when the choice materially affects scope, behavior, risk, or product direction.

## Agent roster

| Agent | Primary charter |
| --- | --- |
| [Orchestrator](orchestrator.agent.md) | Plan, delegate, coordinate, and integrate |
| [Observer](observer.agent.md) | Read-only monitoring and risk escalation |
| [Scribe](scribe.agent.md) | Capture candidate lessons and report them to Observer |
| [Product Manager](product-manager.agent.md) | User outcomes, requirements, and acceptance criteria |
| [UI/UX Designer](ui-ux-designer.agent.md) | Interaction flows, layouts, and design consistency |
| [Accessibility Specialist](accessibility.agent.md) | Inclusive interaction and accessibility validation |
| [Software Architect](architecture.agent.md) | System structure, interfaces, and technical decisions |
| [Software Engineer](software-engineer.agent.md) | Implementation and focused code changes |
| [Web App Specialist](web-app-specialist.agent.md) | Web application implementation and browser behavior |
| [iOS App Specialist](ios-app-specialist.agent.md) | Native iOS implementation, platform UX, and build requirements |
| [Android App Specialist](android-app-specialist.agent.md) | Native Android implementation, platform UX, and build requirements |
| [Tester](tester.agent.md) | Test strategy, execution, and defect evidence |
| [Security Specialist](security.agent.md) | Defensive threat analysis and secure-design review |
| [Privacy and Data Specialist](privacy-data.agent.md) | Data minimization, handling, and privacy controls |
| [Network Specialist](network.agent.md) | Network behavior, protocols, and connectivity |
| [CI Specialist](ci.agent.md) | Continuous integration and automated quality gates |
| [DevOps and Release Specialist](devops-release.agent.md) | Build, deployment, reliability, and release readiness |
| [Content Specialist](content.agent.md) | Product copy, help content, and terminology |
| [Marketing Specialist](marketing.agent.md) | Positioning, audience, and go-to-market messaging |
| [Advertising Specialist](advertising.agent.md) | Paid campaign concepts, variants, and measurement |
| [Documentation Specialist](documentation.agent.md) | Developer and user documentation |

For current project rules and status, read the repository's source-of-truth files at task time. Do not treat these charters as product requirements or a snapshot of project status.
