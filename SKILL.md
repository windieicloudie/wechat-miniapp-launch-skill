---
name: wechat-miniapp-launch
description: Plan, design, build, test, register, file, submit, and publish a WeChat Mini Program. Use when a user wants to create or launch a WeChat Mini Program, migrate a prototype into WeChat Developer Tools, prepare registration materials, configure privacy and service categories, complete filing, or resolve review and release blockers.
---

# WeChat Mini Program: design to launch

Guide the user from a validated product concept to a published, maintainable WeChat Mini Program. Treat product design, implementation, platform registration, compliance, review, and release as separate gates. Act as a proactive completeness auditor: identify what is missing before the user has to ask, while giving beginners one concrete action at a time.

## Start by establishing state

Before acting, determine:

- product goal, audience, core recurring task, and v1 boundaries;
- whether a visual prototype already exists and is the approved source of truth;
- repository/framework, local project path, build command, `miniprogramRoot`, and current AppID;
- intended subject type: personal, individual business, or organization;
- monetization needs, sensitive features, backend/data flows, third-party services, and requested permissions;
- current platform stage: idea, implementation, test AppID, formal AppID, uploaded, experience version, filed, under review, or published.

Do not ask the user to repeat information already available in the project or conversation. Inspect the repository and platform state when safe and available.

## Begin with a gap audit

For a new request or a resumed project, read [references/gap-audit.md](references/gap-audit.md) and produce a compact project ledger before prescribing work. Infer as much as possible from conversation history, repository files, build configuration, screenshots, and platform state. Ask only questions whose answers change architecture, eligibility, compliance, cost, or the next irreversible action.

Do not make the user discover missing requirements by repeatedly asking the agent. Proactively surface missing product states, assets, data sources, permissions, privacy items, qualifications, test evidence, registration materials, and release steps. Batch non-blocking questions and continue safe work in parallel.

## Route to the relevant workflow

- For product definition, prototype fidelity, architecture, implementation, or test planning, read [references/product-development.md](references/product-development.md).
- For account type, registration, AppID replacement, upload, privacy, filing, review, and release, read [references/registration-review.md](references/registration-review.md).
- Before declaring any milestone complete, read the relevant section of [references/pitfalls.md](references/pitfalls.md).
- For a first assessment, handoff, resumed project, or “what is missing?” request, read [references/gap-audit.md](references/gap-audit.md).

## Operating rules

1. Maintain a single approved source of truth for visual and interaction decisions. Once the user approves a prototype, implementation must reproduce it rather than reinterpret it. Compare screenshots at the same viewport and device scale.
2. Separate preview data from production logic. A convincing UI is not evidence that personalization, calendars, permissions, persistence, networking, or export actually work.
3. Verify outputs, not just code paths. Test on a physical phone when behavior depends on safe areas, fonts, permissions, canvas, albums, location, storage, or device dimensions.
4. Keep claims, permissions, privacy declarations, code behavior, service category, and review notes consistent. Local-only data still counts as information processed by the Mini Program when the user enters it.
5. Use the least privilege and least data necessary. Do not request location when manual city entry suffices; do not claim server storage when data is local; do not select “no privacy collected” when the app accepts personal information.
6. Treat platform rules, categories, qualifications, fees, and payment eligibility as time-sensitive. Check current official WeChat/Weixin Pay documentation or the live console before giving a definitive answer.
7. Never ask for or expose `AppSecret`. AppID is safe to use in project configuration; secrets belong in protected backend configuration, never client code.
8. Do not conflate upload, experience release, review, and production release. Each is a separate milestone with its own verification.
9. Optimize for user time and token use. Reuse known facts, prefer one structured audit over serial discovery questions, and give paste-ready text or exact console paths instead of generic explanations.
10. Maintain a living ledger of `known`, `verified`, `missing`, `blocked`, `not applicable`, and `later`. Update it after every material milestone instead of restarting discovery.

## Default phase gates

Advance only when the current gate is satisfied:

1. **Definition:** v1 scope, target user, main journey, data/permission map, and monetization assumption are explicit.
2. **Design:** approved screens and states cover empty, loading, error, permission denied, and small-screen behavior.
3. **Implementation:** production logic, persistence, permissions, and exports work; no placeholder data remains on critical paths.
4. **QA:** automated checks pass where available; physical-device regression passes; generated images are inspected from the phone album.
5. **Account:** correct subject and formal AppID are selected; code is not still bound to a test or obsolete subject.
6. **Compliance:** service category, privacy guide, collected-information declarations, permissions, filing, and review copy match the implementation.
7. **Release:** version is uploaded, experience-tested, submitted, approved, then deliberately published.
8. **Post-release:** production smoke test, monitoring/contact route, rollback or hotfix plan, and version record exist.

## Communication for first-time publishers

Give the next action using the exact console path and the exact text to paste when useful. Explain what success looks like and what screenshot/error to return if it fails. Avoid dumping the entire remaining workflow unless the user requests a full plan.

When the user asks for an overview, show only:

1. current phase and last verified milestone;
2. critical missing items that block launch;
3. important but non-blocking risks;
4. the next three actions;
5. decisions that genuinely require the user.

After production launch, capture the actual review outcome, publication steps, production-only defects, and fixes. Add only reusable lessons to this skill; keep product-specific facts in the project ledger.
