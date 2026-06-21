---
exo__Asset_uid: aefdb1a3-ae87-4d4e-93fb-fb989a243c0c
exo__Asset_isDefinedBy: "[[1fa4b6b1-d630-417f-b0e6-c99cf9b938b6]]"
exo__Asset_createdAt: 2026-06-22T01:22:44+05:00
exo__Asset_updatedAt: 2026-06-22T01:22:44+05:00
exo__Asset_createdBy: "[[de20a3f1-7483-4714-ab28-b45f5cf02c76|ExoAssistant]]"
exo__Instance_class:
  - "[[a49f95ba-e0a7-43b9-b9e5-30946d1fce36|req__RequirementBindingClass]]"
exo__Asset_description: Component test (.test.tsx / jsdom). Does NOT satisfy the P0 binding-class floor alone (jsdom is not real-prod-exercising; classified below-floor, like unit).
exo__schema_optionValue: "[[aefdb1a3-ae87-4d4e-93fb-fb989a243c0c]]"
exo__schema_optionLabel: component
exo__schema_optionOrder: 15
exo__Asset_label: req__RequirementBindingClassComponent
aliases:
  - req__RequirementBindingClassComponent
---

# req__RequirementBindingClassComponent

Component test (`.test.tsx` / jsdom — e.g. Playwright Component Testing or jsdom
React component tests). A verification tier **between** `unit` and the real-prod
classes: it exercises a UI component in isolation under a synthetic DOM (jsdom),
not against live Obsidian / a real desktop UI.

Because jsdom is **not** real-prod-exercising, `component` does **NOT** satisfy
the P0 binding-class floor alone — it is classified below-floor, like `unit`
(RFC 0003 §3.6). A P0 requirement bound solely to `component` (or `unit`, or
both) is a floor violation; it needs at least one
`integration`/`e2e`/`gui-bdd`/`ui-acceptance` binding.

Previously component tests collapsed into the `unit` binding-class; this distinct
tier lets the traceability checker classify them separately while keeping the
correct below-real-prod floor semantics.
