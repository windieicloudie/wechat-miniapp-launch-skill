# Proactive gap audit and project ledger

Use this reference at project start, when inheriting an existing Mini Program, before upload/review/release, and whenever the user asks what remains.

## Audit method

1. Read existing conversation decisions and approved visuals.
2. Inspect the repository, project configuration, build scripts, routes, storage, network calls, permission APIs, assets, and generated package.
3. Determine the platform stage and subject type from reliable evidence.
4. Populate the ledger below without asking the user for facts already observable.
5. Classify gaps by launch impact and give a short action plan.

Use these statuses consistently:

- `verified`: supported by code, screenshot, successful test, or platform state;
- `known`: stated by the user but not yet verified;
- `missing`: required and absent;
- `blocked`: cannot proceed without a specific user choice, permission, qualification, or external result;
- `later`: intentionally outside the current version;
- `not applicable`: checked and irrelevant to this product.

Never label an item `verified` merely because code exists. Runtime, visual, permission, export, and platform behavior require appropriate evidence.

## Completeness ledger

### Product

- target user and problem;
- core repeat-use journey;
- v1 scope and explicit exclusions;
- free/advertising/payment/subscription model;
- success metrics and post-launch learning plan;
- claims and regulated/high-risk positioning.

### Experience and content

- approved design source of truth;
- all routes and navigation;
- empty, loading, error, offline, denied-permission, and missing-data states;
- responsive/safe-area/small-screen behavior;
- copy, localization, accessibility, contrast, and font fallbacks;
- name, avatar, introduction, screenshots, and share presentation.

### Data and logic

- inputs, algorithm/content source, update frequency, accuracy limits, and fallbacks;
- generic vs personalized behavior and output diversity;
- local/server storage, retention, edit/delete route, and migrations;
- networking, domains, caching, offline behavior, and third parties;
- backend, secrets, authentication, abuse controls, and operational ownership where applicable.

### WeChat implementation

- framework/toolchain versions and supported syntax;
- source directory, build output, `miniprogramRoot`, and package size;
- formal AppID vs test/obsolete AppID;
- API permissions and base-library compatibility;
- physical-device evidence for forms, storage, navigation, permissions, and image export;
- release candidate version frozen and reproducible.

### Registration and compliance

- subject type is valid, active, authorized, and compatible with monetization;
- service category and required qualifications;
- privacy guide matches code and manual inputs;
- collected-information switch, permission purposes, user contact, and delete route;
- filing status and required identity/SMS verification;
- review description, service description, test instructions/account, and version notes;
- current platform rules verified from official/live sources when time-sensitive.

### Release and operation

- upload, experience version, regression test, review, approval, and publish states tracked separately;
- production smoke test from QR/search/share entry;
- error monitoring or support route appropriate to the product;
- rollback/hotfix procedure and version record;
- analytics only when authorized and disclosed;
- post-launch review date and decision criteria for the next version.

## Gap priorities

- **P0 launch blocker:** prevents build, upload, review, filing, publication, core task completion, or lawful operation.
- **P1 material risk:** likely rejection, data mismatch, broken device behavior, misleading result, or serious visual regression.
- **P2 improvement:** valuable but can safely wait for a later version.

Report gaps in priority order. Each gap needs: evidence, impact, exact next action, owner, and verification condition. Avoid a long generic checklist containing items already complete or not applicable.

## Token-efficient interaction

- Ask at most a small batch of high-impact questions at a time; prefer one when it blocks the immediate next step.
- Offer mutually exclusive choices only when each choice changes the result.
- Give paste-ready registration/review/privacy text derived from actual behavior.
- When a screenshot would resolve several unknowns, request one screenshot instead of several textual answers.
- When safe, inspect code/config first and then ask only about business intent or external facts.
- Preserve the ledger across turns and summarize deltas, not the entire history.

## Recommended compact output

```text
阶段：<current phase>
已验证：<last verified milestone>

P0 缺口
- <gap — impact — next action — verification>

P1 风险
- <risk — mitigation>

接下来三步
1. ...
2. ...
3. ...

需要用户决定
- <only decisions that cannot be inferred>
```

Omit empty sections. For a beginner, follow the audit with only the first actionable step; keep the remaining plan available without overwhelming them.
