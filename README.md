# Second Brain — Adaptive Life Interview & Memory Curation

一款与模型无关的 Agent Skill，通过自适应人生访谈，帮助用户构建由自己掌控、兼容 Obsidian 的个人知识库，并以普通 Markdown 文件保存。

A model-agnostic Agent Skill that uses an adaptive life interview to help users build a user-controlled personal knowledge base in ordinary Markdown files compatible with Obsidian.

## Important: grant access before use

**Before starting, explicitly enable file access for your AI agent in its project/workspace settings and grant access only to the knowledge-base directory you want it to use.** The skill cannot grant itself permissions. The agent must be able to read existing files and write updates to `personal_data/`.

Access controls vary by agent and operating environment. Follow the settings and permission flow of your chosen tool. If the runtime cannot read/write files, the skill can still conduct the interview conversationally, but it must not claim that files were saved.

## What it does

- Starts with two lightweight background questions: age/life stage and country/region. Exact birth date is optional.
- Discovers interview topics from the user's answers instead of forcing a fixed life questionnaire.
- Uses dynamic depth-first exploration while letting the user choose questions, combine answers, change topics, skip, or stop at any time.
- Handles ambiguity and apparent contradictions by asking for clarification rather than guessing.
- Distinguishes user-stated information, self-interpretation, reported information, AI inference, and uncertainty when the distinction matters.
- After the interview, updates the appropriate `personal_data/` Markdown files and verifies writes when possible.
- Preserves chronology, changes in views, and the user's authority to correct or delete memories.

## What it does not do

- It does **not** create or maintain a `conversations/` folder or a separate interview transcript.
- It does not bypass file permissions, promise automatic access, or report a write as successful without verification.
- It does not require the user to answer every topic or infer that a skipped topic indicates a problem.
- It does not include personal memory files in this public repository.

## Install

Copy the entire repository folder into the skill directory supported by your agent. Keep the folder structure intact so the skill and its supporting reference stay together. For example, in a repository using the Agent Skills convention, the installed files should be:

```text
.agents/skills/second-brain/SKILL.md
.agents/skills/second-brain/references/memory-schema.md
```

The acceptance test plan is at [`tests/acceptance-tests.md`](tests/acceptance-tests.md). Other agents may use a different skills directory. Check your agent's documentation and start a new session if required.

## Use

Try prompts such as:

- “Start my Second Brain interview.”
- “Continue building my personal memory.”
- “Update my Second Brain with this change.”
- “Review my current profile for outdated or unsupported claims.”

Before an initialization interview, select the intended knowledge-base root and grant the agent the necessary access. The expected durable memory destination is `personal_data/`.

## Default memory structure

```text
personal_data/
├── 00_core_profile/profile.md
├── 01_background_and_life_history/
├── 02_personality_and_behavior/personality_and_behavior.md
├── 03_values_beliefs_and_worldview/
├── 04_relationships_and_social_environment/
├── 05_interests_knowledge_and_exploration/
├── 06_ambitions_goals_and_plans/
├── 07_current_life/current.md
├── 08_emotions_and_reflections/current.md
└── 09_creative_work/
```

See [`memory-schema.md`](references/memory-schema.md) for file purposes and naming guidance.

## Privacy note

A public repository contains the reusable skill instructions only. Keep your `personal_data/` directory private and outside this project repository. Review your AI tool's own data handling and file-access settings; local Markdown storage does not by itself determine how your model provider processes chat content.

## Design references

The implementation borrows general structural ideas from public Agent Skills such as [`karpathy-llm-wiki`](https://github.com/Astro-Han/karpathy-llm-wiki) (a concise schema layer plus supporting references) and [`grill-me`](https://github.com/stevegsax/grill-me) (clear interaction boundaries). This project has its own interview logic and memory schema; it does not copy their content.

## License

MIT. See [`LICENSE`](LICENSE).
