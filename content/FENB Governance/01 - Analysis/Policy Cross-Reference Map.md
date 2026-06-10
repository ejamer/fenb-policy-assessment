---
type: analysis
title: "Policy Cross-Reference Map"
created: 2026-06-09
updated: 2026-06-09
tags: [analysis, cross-reference, inconsistency]
---

# Policy Cross-Reference Map

This note maps how policies reference each other, identifies the hub policy (2.1), and flags stale references resulting from the April 2026 consolidation.

---

## Reference Network

### Who references whom (Layer 3 → Layer 3)

| Policy referencing → | 2.1 | 2.2 | 2.3 | 2.6 | 2.7 | 2.10 | 2.11 | 2.12 | 2.14 | 2.17 | 2.18 |
|---------------------|-----|-----|-----|-----|-----|------|------|------|------|------|------|
| **2.1** Safe Sport | — | | | | ✓ | ✓ | ✓ | | | ✓ | |
| **2.2** Risk Mgmt | ✓ | — | | | | | | ✓ | | ✓ | |
| **2.3** DEI | ✓ | | — | | ✓ | | | | | | |
| **2.5** Official Language | ✓ | | | | | | | | | | |
| **2.6** Financial Mgmt | ✓ | ✓ | | — | | | | | ✓ | | |
| **2.7** HR | ✓ | ✓ | ✓ | | — | ✓ | | | | | |
| **2.10** Volunteer Mgmt | ✓ | | ✓ | | ✓ | — | | | | | ✓ |
| **2.11** Privacy | ✓ | ✓ | | ✓ | ✓ | | — | | | | |
| **2.12** Insurance | ✓ | ✓ | | ✓ | | | ✓ | — | | ✓ | |
| **2.14** COI/Ethics | ✓ | ✓ | | ✓ | ✓ | | | | — | | |
| **2.17** Crisis Mgmt | *(stale)* | ✓ | | | | | | ✓ | | — | |
| **2.18** IDR | | | | | | ✓ | | | | | — |

**2.1 Safe Sport is the hub** — referenced by every other policy except 2.18.

---

## Stale References — The April 2026 Consolidation Problem

### What happened
In April 2026, FENB consolidated at least four former policies into a single integrated 2.1 Safe Sport, Conduct, and Athlete Protection Policy:
1. Former Safe Sport and Athlete Welfare Policy (likely Section 2.13)
2. Former Code of Conduct Policy
3. Former Anti-Harassment Policy
4. Former Communications and Social Media Policy (possibly formerly Section 2.1)

When this consolidation occurred, **the cross-references in other policies were not systematically updated**. Two types of stale references resulted:

### Type A: "Communications and Social Media Policy (Section 2.1)" — appears in 2 policies

| Policy containing stale reference | Stale text | What it should say |
|----------------------------------|------------|-------------------|
| [[2.11 Privacy and Data Protection]] | "Communications and Social Media Policy (Section 2.1)" | Safe Sport, Conduct, and Athlete Protection Policy (Section 2.1), Section E |
| [[2.17 Crisis and Emergency Management]] | "Communications and Social Media Policy (Section 2.1)" | Safe Sport, Conduct, and Athlete Protection Policy (Section 2.1), Section E |

**Significance:** The "Communications and Social Media" label implies a separate, standalone policy. Anyone who finds that reference and looks for it will not find a separate policy — because it no longer exists as a standalone. The communication standards are now embedded in Section E of 2.1.

### Type B: "Safe Sport and Athlete Welfare Policy (Section 2.13)" — appears in 1 policy

| Policy containing stale reference | Stale text | What it should say |
|----------------------------------|------------|-------------------|
| [[2.17 Crisis and Emergency Management]] | "Safe Sport and Athlete Welfare Policy (Section 2.13)" | Safe Sport, Conduct, and Athlete Protection Policy (Section 2.1) |

**Significance:** Section 2.13 does not exist in the current policy manual. The former 2.13 was likely the standalone Safe Sport and Athlete Welfare policy before consolidation.

---

## The "Section 2.1" Name Ambiguity

Before April 2026, the evidence strongly suggests:
- Section 2.1 = Communications and Social Media Policy
- Section 2.13 = Safe Sport and Athlete Welfare Policy
- Other standalone policies = Code of Conduct, Anti-Harassment

After April 2026 consolidation:
- Section 2.1 = Safe Sport, Conduct, and Athlete Protection Policy (absorbs all the above)
- Sections 2.13, and the former 2.1 standalone = No longer exist

This creates a specific confusion: when other policies reference "Section 2.1," are they referring to the *former* Section 2.1 (Communications) or the *current* Section 2.1 (Safe Sport)? In almost all cases, the context makes the intended referent clear — but the stale label in the reference text doesn't.

---

## Fix Required at Next Policy Review

At the April 2028 policy review (or earlier), the following changes should be made:

1. **In 2.11 (Privacy):** Update the "Communications and Social Media Policy (Section 2.1)" reference to "Safe Sport, Conduct, and Athlete Protection Policy (Section 2.1), Section E — Communications and Social Media Conduct"

2. **In 2.17 (Crisis):**
   - Update "Safe Sport and Athlete Welfare Policy (Section 2.13)" → "Safe Sport, Conduct, and Athlete Protection Policy (Section 2.1)"
   - Update "Communications and Social Media Policy (Section 2.1)" → "Safe Sport, Conduct, and Athlete Protection Policy (Section 2.1), Section E"

3. **System-wide:** Conduct a complete audit of all policy cross-references before the 2028 review to catch any additional stale references that may have been missed.

---

## Policies with No Inbound References

These policies are not referenced by any other policy in the manual — meaning they exist somewhat in isolation:

- **[[2.3 Diversity, Equity, and Inclusion]]** — referenced in 2.7 and 2.10, but not in 2.1 (Safe Sport), which discusses discrimination. A stronger cross-link between 2.1 and 2.3 would reinforce that DEI is not separate from Safe Sport.
- **[[2.5 Official Language]]** — referenced only in its own "Related Policies" (2.1 and 2.4). Given the bilingualism requirements in NB, this policy could logically be referenced in HR (2.7) and in the governance documents.
- **[[2.18 Internal Dispute Resolution]]** — referenced in 2.10 (Volunteer Management). Not referenced in 2.7 (HR), despite 2.7 having a full grievance and conflict resolution section that effectively covers the same ground.

The last point — 2.7 HR and 2.18 IDR potentially overlapping — is worth examining. The grievance process in 2.7 (§13) describes a parallel internal process to what 2.18 establishes. These should be explicitly reconciled to confirm they are the same process, or if they are different, to explain when each applies.
