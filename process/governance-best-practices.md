# CNCF Project Governance — Best Practices and Recommendations

**Date:** 2026-07-05
**Author:** Karena Angell, CNCF TOC
**Based on:** CNCF Projects Governance Analysis by the TOC (71 graduated and incubating projects evaluated)
**Status:** Draft for TOC review

---

## Purpose

This document provides governance best practices and recommendations for CNCF projects at each maturity level. The recommendations are grounded in data from the TOC's governance analysis of 71 projects, which identified the governance patterns that predict long-term project health and the patterns that lead to post-graduation decline.

The recommendations are cumulative — each level builds on the previous.

---

## What the Data Shows

- **Multi-org projects at sandbox time** graduate at **2.07x** the rate of single-org projects (59.1% vs 28.6%)
- Projects with **steering committees** or **org-balanced voting** have the highest governance maturity and sustain diversity longer
- **7 of 35 graduated projects** (20%) now show post-graduation governance concentration — **all 7 lacked org-balance mechanisms at incubation**
- The gap between listed maintainer diversity and actual contribution concentration is a recurring pattern
- **Governance documentation alone does not prevent concentration** — structural mechanisms are required

---

## Sandbox

**Principle:** Establish the foundation. Projects entering sandbox may be single-org — that's acceptable. The goal is to set up governance infrastructure that enables diversification, not to require it.

### Required

1. **Open source license.** Apache-2.0 preferred. All dependencies must be on the [CNCF allowed license list](https://github.com/cncf/foundation/blob/main/policies-guidance/allowed-third-party-license-policy.md) or have a Governing Board exception.

2. **GOVERNANCE.md.** Discoverable governance documentation — at repo root or in a community repo. Must cover how decisions are made, how maintainers are added/removed, and the project's code of conduct. See the [CNCF governance templates](https://contribute.cncf.io/maintainers/templates/) and [governance introduction](https://contribute.cncf.io/resources/templates/governance-intro/) for starting points.

3. **MAINTAINERS file with affiliations.** Complete list of current maintainers with names, GitHub handles, and organizational affiliation. Affiliations must be kept current. See the [CNCF MAINTAINERS template](https://github.com/cncf/project-template/blob/main/MAINTAINERS.md).

4. **Code of Conduct.** Adopt the CNCF Code of Conduct or a project CoC based on it. Cross-link from governance and contributing docs.

5. **CONTRIBUTING.md.** Documented process to submit issues and contributions.

### Recommended

6. **Contributor ladder.** Define at least two levels (contributor → maintainer). Projects that define intermediate roles (reviewer, committer) produce more diverse maintainer pools over time. See the [CNCF contributor ladder template](https://github.com/cncf/project-template/blob/main/CONTRIBUTOR_LADDER.md) and [guidance on incentivizing contributors to move up the ladder](https://contribute.cncf.io/projects/best-practices/community/contributor-growth/incentivizing-contributors/).

7. **Inactivity policy.** Define what constitutes maintainer inactivity and what happens (emeritus status, removal). Suggested threshold: 12 months of no contributions.

8. **Public communication channels.** At least one public channel (Slack, mailing list, Discord) documented and accessible.

9. **Vendor neutrality awareness.** If the project is single-org, acknowledge it in the governance doc and state the intent to diversify. Projects that acknowledge concentration early are better positioned to address it. See the [CNCF vendor neutrality guidelines](https://contribute.cncf.io/maintainers/community/vendor-neutrality/).

---

## Incubating

**Principle:** Demonstrate governance that works in practice. Incubation is where the TOC evaluates whether the project can sustain itself independently of any single company. The governance analysis shows this is the critical stage — every graduated project now classified Critical lacked structural protections at incubation.

### Required (cumulative with Sandbox)

10. **Org-balanced voting for governance decisions.** One vote per organization, regardless of maintainer count. This is the single most effective anti-concentration mechanism identified in the governance analysis.

    Each organization gets one vote on governance decisions (steering elections, governance changes, strategic direction), regardless of how many maintainers that organization employs. If two maintainers are employed by Company X, two by Company Y, two by Company Z, and one maintainer is an independent individual, a total of four organization votes are possible.

    Technical decisions (code review, merge, release) remain lazy consensus among all maintainers — org-balanced voting protects governance, not day-to-day engineering.

11. **Documented contributor ladder with multiple roles.** At minimum: contributor → reviewer → maintainer. Specific requirements at each level. The path must not require sponsorship from the dominant organization. See the [CNCF contributor ladder template](https://github.com/cncf/project-template/blob/main/CONTRIBUTOR_LADDER.md).

    Projects with intermediate roles (reviewer or committer between contributor and maintainer) produce more diverse maintainer pools because they give external contributors a visible progression path and build trust before maintainer nomination.

12. **Maintainer lifecycle demonstrated.** Not just documented — show evidence of the lifecycle being applied (maintainer additions, emeritus transitions, or removals). The governance analysis found multiple projects with documented lifecycle processes that have never been used. See the [maintainer council template](https://contribute.cncf.io/resources/templates/governance-maintainer/) for lifecycle documentation patterns.

13. **Vendor neutrality enforced, not just stated.** The governance doc must include structural mechanisms, not just value statements. Review project website, documentation, and security contacts for single-vendor references that violate [CNCF vendor neutrality guidelines](https://contribute.cncf.io/maintainers/community/vendor-neutrality/).

    Common issues found during DD triage:
    - Project website linking to a single vendor's commercial product page
    - All security contacts using one company's email domain
    - Build/release tooling configured with vendor-specific emails
    - "Enterprise offerings should point to the enterprise page of the project that features all vendors equally"

14. **Security response roles documented.** Not just where to report — document who is responsible for triaging and responding. Named individuals or a committee with defined membership and a clear escalation path.

15. **Related projects disclosed.** If maintainers operate related projects in other foundations (Linux Foundation, Apache, Eclipse, etc.), disclose the relationship, shared maintainers, and scope boundaries.

### Recommended

16. **Steering committee with org caps.** Separates governance authority from code authority. Recommended structure: 5 seats, max 2 per organization. Initially seats may be empty — they represent the community the project is building toward. See the [steering committee elections template](https://contribute.cncf.io/resources/templates/governance-elections/) and [leadership selection guidance](https://contribute.cncf.io/projects/best-practices/governance/leadership-selection/).

    Projects that separate governance (steering) from execution (maintainers) sustain diversity longer because committee membership has org caps even when maintainer composition shifts.

17. **Emeritus enforcement.** Apply the inactivity policy. Move inactive maintainers to emeritus status. The governance analysis found projects listing inactive external maintainers for years to inflate apparent diversity.

18. **CODEOWNERS mapping.** Code and doc ownership in GitHub matches documented governance roles.

19. **Public meeting schedule.** Regular community meetings with published notes or recordings. Integration with CNCF calendar.

### Governance practice period

For projects with **>75% LFX org dependency** and no org-balance mechanism, the TOC recommends implementing governance changes and demonstrating them in practice for **3 months** before the DD continues. Exit criteria:

- Org-balanced voting or steering committee adopted
- ≥3 governance meetings with published minutes
- At least one governance decision through the new process
- No regression in LFX org dependency

This is not punitive — it verifies governance works under real conditions. Projects with lower concentration or existing structural protections may proceed without a practice period.

---

## Graduating

**Principle:** Prove survivability. Graduation means the project can sustain itself if any single company exits. The governance must demonstrate — not just document — that no single organization controls the project's direction.

### Required (cumulative with Incubating)

20. **Maintainers from at least 2 organizations.** Required by existing graduation criteria. The governance analysis recommends verifying this through **LFX Insights org dependency data**, not just the MAINTAINERS file. The gap between listed diversity and actual contribution dependency is a known pattern.

21. **Governance/code alignment verified.** Steering committee diversity must match actual committer pool diversity. Multiple graduated projects have governance bodies with external representation while the actual code maintainers remain 100% single-org.

22. **Succession planning documented.** What happens if the primary maintainer organization exits? Graduated projects should document the contingency — who takes over releases, who holds infrastructure credentials, who manages the security response process.

23. **Contributor ladder producing external maintainers.** The ladder must have demonstrably produced maintainers from outside the dominant organization. A documented ladder that has never produced an external maintainer is not evidence of openness.

### Recommended

24. **Advisory board or end-user representation.** Formal seats for adopters in governance decisions — giving production users a voice alongside maintainers.

25. **Post-graduation governance health check.** The TOC recommends annual health checks on maintainer org composition for graduated projects. Multiple graduated projects currently show concentration concerns that would have been caught with monitoring.

26. **OpenSSF Best Practices silver or gold badge.** Suggested, not required — but projects pursuing graduation should aim for silver (87% or higher) as evidence of security maturity.

---

## Anti-Patterns to Avoid

These patterns, identified across the 71-project analysis, correlate with governance decline:

| Anti-Pattern | What it looks like |
|:---|:---|
| **Cosmetic diversity** | Maintainer list has external names but contributions are 80%+ one org |
| **Voter cap without org balance** | Caps how many voters one company has, but they still outnumber everyone |
| **Governance/code divergence** | Steering committee is diverse but code maintainers aren't |
| **Documented but never used** | Contributor ladder, emeritus process, election process — all documented, never applied |
| **Silent maintainership** | Zero human engagement in PRs; bot-only interactions |
| **Foundation shopping** | Splitting one product into multiple projects across different foundations with shared maintainers |

---

## Exemplary Governance Patterns

These patterns represent governance that works and can be referenced by projects:

| Pattern | What makes it effective |
|:---|:---|
| **Org-balanced voting** | One vote per org equalizes governance voice regardless of employer headcount |
| **Steering committee with org caps** | Max 1-2 members per org; separates governance from code authority |
| **Multi-level contributor ladder** | Intermediate roles (reviewer, committer) give external contributors a visible path |
| **Active emeritus process** | Documented and applied — inactive maintainers transitioned, not left as cosmetic diversity |
| **Community manager role** | Non-technical role for community health, onboarding, CNCF interface |
| **Affiliation disclosure requirement** | Maintainers must update affiliation within 30 days of change |
| **End-user governance seats** | Formal adopter representation in governance decisions |

---

## How This Document Relates to Existing Criteria

This document does **not** replace the incubation or graduation criteria. It supplements them with:

**Key CNCF resources:**
- [CNCF Governance Overview](https://contribute.cncf.io/community/governance/)
- [Governance Templates](https://contribute.cncf.io/maintainers/templates/) — maintainer council, steering committee elections, subprojects
- [Governance Introduction](https://contribute.cncf.io/resources/templates/governance-intro/)
- [Contributor Ladder Template](https://github.com/cncf/project-template/blob/main/CONTRIBUTOR_LADDER.md)
- [GOVERNANCE.md Template](https://github.com/cncf/project-template/blob/main/GOVERNANCE.md)
- [Vendor Neutrality Guidelines](https://contribute.cncf.io/maintainers/community/vendor-neutrality/)
- [Leadership Selection Guidance](https://contribute.cncf.io/projects/best-practices/governance/leadership-selection/)
- [Incentivizing Contributors](https://contribute.cncf.io/projects/best-practices/community/contributor-growth/incentivizing-contributors/)
- [CNCF Allowed License Policy](https://github.com/cncf/foundation/blob/main/policies-guidance/allowed-third-party-license-policy.md)
- [CNCF License Exception Database](https://cncf-license-exceptions.netlify.app/)

It supplements the criteria with:

- **Data-driven rationale** for why specific governance mechanisms matter
- **Specific patterns** for projects to follow at each level
- **Anti-patterns** to recognize and avoid
- **Practice period guidance** for the TOC's DD process

The [incubation application template](https://github.com/cncf/toc/blob/main/.github/ISSUE_TEMPLATE/template-incubation-application.md) and [graduation application template](https://github.com/cncf/toc/blob/main/.github/ISSUE_TEMPLATE/template-graduation-application.md) remain the authoritative checklists. This document provides the "why" and "how" behind the governance items on those checklists.
