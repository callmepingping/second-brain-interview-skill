# Personal Memory Schema

This document defines the default role of each folder under `personal_data/`. If the user's existing knowledge base has a clearly established compatible schema, preserve it instead of imposing a migration.
In the case of any special circumstances, the AI should appropriately adjust or the structure or create new folders.

## `00_core_profile/profile.md` — foundational profile

A concise, revisable overview of background, education/work when shared, stable long-term interests, and context that helps an agent understand the user. It is not a substitute for detailed history, relationships, or value-development records.

## `01_background_and_life_history/` — important life history

Store meaningful experiences and their development. Prefer one file per substantial episode or long-running theme. When dates are known, use `YYYY-MM-DD-YYYY-MM-DD_history.md`; do not invent precise dates. If exact dates are unknown, choose a truthful approximate naming scheme and explain it in the file.

## `02_personality_and_behavior/personality_and_behavior.md` — patterns and behavior

Store recurring behavior patterns, habits, ways of working, and the user's own descriptions. Distinguish self-reported patterns from AI hypotheses. Avoid essentializing or diagnostic labels.

## `03_values_beliefs_and_worldview/` — values and ideas

Use one file per meaningful topic or development path, e.g. `YYYY-MM-DD_topic.md`. Preserve why an idea matters, experiences that shaped it, uncertainties, and changes over time.

## `04_relationships_and_social_environment/` — people and relationships

Use one file per significant person, relationship, group, or event, e.g. `YYYY-MM-DD_person-or-event.md`. Keep only information relevant to understanding the user's life and relationships; avoid unnecessary sensitive details about third parties.

## `05_interests_knowledge_and_exploration/` — interests and learning

Record long-term interests, fields of exploration, developing knowledge, and changes in intellectual direction. Distinguish current interest from a past phase.

## `06_ambitions_goals_and_plans/` — aims and plans

Record meaningful goals, motivations, milestones, decisions, and changes. Mark status and time context so old plans do not appear current indefinitely.

## `07_current_life/current.md` — current circumstances

Maintain a concise view of current projects, routines, responsibilities, environment, and active concerns where shared. Replace stale current-state statements when new information arrives; preserve major past circumstances in life-history records when relevant.

## `08_emotions_and_reflections/current.md` — recent feelings and reflection

Capture recent emotions, concerns, unresolved questions, and evolving self-understanding that the user chose to share. Treat this as time-bound, not a permanent psychological profile. Distinguish explicit self-report from inference.

## `09_creative_work/` — projects and original work

Use `YYYY-MM-DD_work-name.md` when a meaningful creation date is known. Record project purpose, motivation, important decisions, evolution, and outcomes. For complete works, preserve the user's original text when appropriate and authorized; never present an AI rewrite as the user's original.

## Common metadata principles

For meaningful records, use a lightweight header or section that fits the file's existing style:

- **Time of event**: when it happened, if known.
- **Time described**: when the user recalled or described it, if known.
- **Last updated**: when the file was actually updated, if known.
- **Information status**: user-stated, user interpretation, reported information, AI hypothesis, or uncertain, when the distinction matters.
- **Source**: a real, inspectable file path or external reference when available. Never invent a link. The interview skill does not create a transcript archive, so do not cite `conversations/` files that do not exist.

The same experience may be referenced by several files, but each file should have one clear primary purpose. Use Obsidian links when the target file exists. Avoid copying a full story into every related folder.
