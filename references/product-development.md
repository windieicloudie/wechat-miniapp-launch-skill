# Product, design, implementation, and QA

## 1. V1 product brief

Produce a compact brief before building:

- one-sentence user problem;
- target audience and context of use;
- single primary action and return-use trigger;
- v1 must-have, later, and explicitly excluded features;
- free, advertising, transaction, or subscription assumption;
- content/algorithm source, update frequency, and accuracy boundary;
- platform target and subject/qualification constraints;
- success metrics such as activation, task completion, retention, save/share, and error rate.

Resolve high-impact ambiguity early. Examples: whether recommendations are generic or personalized; whether an algorithm is local, server-based, editorial, or sourced online; whether “location” means GPS or a manually entered city; and whether the product makes entertainment, lifestyle, medical, financial, or fortune-telling claims.

## 2. Data and permission map

For each feature record:

| Feature | Input | Processing | Storage | Network/third party | Permission | User control |
|---|---|---|---|---|---|---|
| Example | Date entered by user | Local calculation | Device local storage | None | None | Edit/delete |

Use this map to drive architecture, privacy declarations, permission prompts, test cases, and review notes. Reconcile it again before submission.

## 3. Prototype-to-code fidelity

When a prototype is approved:

1. Inventory design tokens: background, text, semantic colors, typography, spacing, radius, borders, shadows, and safe-area behavior.
2. Inventory every screen and state, including empty, selected, permission denied, loading, and exported-image states.
3. Implement reusable tokens/components instead of approximating values per page.
4. Capture implementation screenshots at the same dimensions as the approved prototype.
5. Compare background tint, font family and weight, color luminance, card proportions, alignment, wrapping, and information hierarchy.
6. Fix visual deltas before adding unrelated design changes.

Do not silently substitute system fonts, flatten textured backgrounds, remove colored states, shrink calendar swatches, or redesign an approved layout during migration. If the platform cannot reproduce a detail, explain the limitation and obtain approval for the closest substitute.

## 4. Architecture and production logic

Keep these concerns separate:

- domain calculation/content rules;
- profile and preference persistence;
- view models and UI rendering;
- permission adapters;
- image/canvas export;
- network services, caching, offline/error states;
- analytics and diagnostics, if authorized.

For Taro or other compiled frameworks:

- confirm which directory Developer Tools opens and which directory `miniprogramRoot` points to;
- run typecheck/lint/build independently so the failing stage is obvious;
- inspect the generated package, not only source files;
- confirm the target base library supports emitted syntax; avoid optional chaining or other unsupported syntax when the project disables ES6 transforms;
- never hand-edit generated output as the source of truth.

For personalized or calendar recommendations:

- document inputs, defaults for missing fields, timezone/location assumptions, algorithm version, and fallback behavior;
- ensure personalization changes outputs in a meaningful but non-degenerate way;
- test diversity across weeks/months and compare generic vs personalized modes;
- do not present a static rotation as a precise personalized result;
- if external daily data is promised, implement source retrieval, validation, caching, and failure behavior before calling the product complete.

## 5. QA and release candidate

### Static checks

- typecheck, lint, build;
- no obsolete AppID, debug endpoint, placeholder, test credential, or unimplemented critical button;
- package size and subpackage configuration;
- page routes and navigation;
- privacy/permission APIs found in source match declared use;
- local storage keys and migrations are stable.

### Physical-device regression

- first launch and relaunch;
- smallest supported screen and a representative large screen;
- safe areas, bottom navigation, scroll reachability, keyboard overlap;
- font availability and fallback;
- form edit/save/persistence and missing optional data;
- permission allow, deny, deny permanently, and settings recovery;
- offline/slow network when networking exists;
- generated calendar/wallpaper saved from the phone album and inspected at full resolution;
- text contrast on every color swatch;
- personalized results actually change after profile edits;
- no stale data after switching date, month, city, or profile.

Record the release candidate version and do not mutate it during review unless a new version is intentionally uploaded.
