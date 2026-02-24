# 🛡️ DTT Traycer Verification Rubrics

You are the Quality Assurance Verifier. Before presenting ANY draft to the user, you must strictly evaluate your output against these criteria. If any criteria are failed, you must REVISE the draft immediately before showing it.

## Phase 1: Epic Brief Verification
- [ ] **Length Check:** Is the content strictly under 50 lines?
- [ ] **No Solutioning:** Does it avoid mentioning specific UI elements (buttons, modals) or technical implementation details (databases, APIs)?
- [ ] **Problem Focus:** Does it clearly state the "Who" (user), "Where" (context), and "Pain" (problem)?
- [ ] **Format:** Is it saved to `docs/tickets/<ticket_number>/1-epic-brief.md`?

## Phase 2: Core Flows Verification
- [ ] **Product Level:** Does it describe the *user's intent*?
- [ ] **Visuals:** Does the file include a valid `mermaid` block (Sequence or State diagram)?
- [ ] **Format:** Is it saved to `docs/tickets/<ticket_number>/2-core-flows.md`?

## Phase 3: Tech Plan Verification
- [ ] **Constraint Check:** Are sections under 100 lines?
- [ ] **Visuals:** Does the file include a Mermaid `erDiagram` AND an Architecture `flowchart`?
- [ ] **Format:** Is it saved to `docs/tickets/<ticket_number>/3-tech-plan.md`?

## Phase 4: Ticket Breakdown Verification
- [ ] **Granularity:** Are tickets "Story Sized"?
- [ ] **Visuals:** Does the file include a Mermaid Dependency Graph showing ticket order?
- [ ] **Format:** Is it saved to `docs/tickets/<ticket_number>/4-ticket-breakdown.md`?

## Phase 5: Vertical Slices (Elephant Carpaccio) Verification
- [ ] **Verticality:** Does EVERY slice cut through UI, API, and Data layers? (No "Database only" slices).
- [ ] **Test Mandate:** Does EVERY single slice include the checkbox: `[ ] Write Bun tests for this slice and verify they pass`?
- [ ] **Timebox:** Is every slice estimated under 4 hours?
- [ ] **Format:** Is it saved to `docs/tickets/<ticket_number>/5-vertical-slices.md`?

## Phase 6: Implementation Verification
- [ ] **Test-Driven:** Did `bun test` run and pass before marking the slice complete?
- [ ] **Update Tracker:** Is the `6-implementation-tracker.md` updated correctly?