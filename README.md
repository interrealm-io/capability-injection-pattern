Capability Injection Is the New Dependency Injection for AI

For two decades, Dependency Injection (DI) has been the invisible infrastructure of modern software. It solved a fundamental problem: software components should not construct their own dependencies. Instead, dependencies are declared and resolved by a container.

The result was software that became loosely coupled, testable, and composable. The pattern was so correct that it faded into the background. Today, DI is assumed.

AI agent systems are now facing an equivalent problem — but with authority, not objects.

Most AI agents today operate with static permissions, hardcoded tools, and broad service-account access. Capabilities are embedded into the agent or environment rather than granted dynamically. This creates tightly coupled systems that are difficult to audit, dangerous to delegate, and nearly impossible to reason about at scale.

This is the pre-DI era of AI.

The core insight is simple: authority should be injected the same way dependencies are injected.

I call this pattern Capability Injection (CI).

In Capability Injection, agents do not possess permissions. They declare the capabilities they require for a specific purpose. A governing layer — a realm — evaluates the request, resolves the human principal, validates policy, and injects a scoped, time-bound delegation token. The agent executes strictly within that scope and never holds standing privileges.

The structural parallel to DI is exact. Interfaces map to capability declarations. Implementations map to capability providers. The container becomes a realm. Dependency scope becomes temporal scope. Runtime resolution becomes dynamic authorization.

This is not a metaphor. It is the same architectural move applied to a different dimension of the system.

Critically, Capability Injection must be grounded in human identity. The realm derives authority from an existing identity substrate such as LDAP or Active Directory. Every injected capability is ultimately traceable to a human principal, for a specific purpose, for a limited time. Without this grounding, CI collapses into just another flavor of IAM.

A key rule follows: authority must be requested, not assumed. Capabilities that expand external power — data access, messaging, financial actions — must be explicitly declared by the agent and explicitly granted by the realm. The realm may inject guardrails automatically (logging, policy checks, rate limits), but it must never silently expand authority.

Why does this matter?

Dependency Injection made software composable. Capability Injection makes AI composable.

Without CI, AI agents are privileged monoliths. With CI, agents become governed participants in a system — testable with sandboxed capabilities, auditable in production, and safe to delegate across organizational boundaries.

The industry already contains fragments of this idea: OAuth scopes, cloud IAM conditions, workload identity. What’s been missing is a unifying abstraction that treats authorization as a first-class, injectable concern.

That abstraction is Capability Injection.

Just as DI didn’t invent inversion of control but made it usable at scale, CI doesn’t invent delegation — it makes AI governance legible, rigorous, and inevitable.

Years from now, this will feel obvious.
That’s how you know the pattern is right.
