<div align="center">
  <img src="assets/hero.svg" alt="WeChat Mini Program Launch Skill" width="100%" />
  <h1>Find every launch gap before review finds it for you</h1>
  <p><strong>A proactive Agent Skill for taking a WeChat Mini Program from idea to production.</strong></p>
  <p><a href="README.md">中文</a> · <a href="SKILL.md">Skill</a> · <a href="references/gap-audit.md">Gap audit</a></p>
</div>

`wechat-miniapp-launch` inspects the conversation, repository, configuration, screenshots, and platform stage before asking questions. It identifies missing product states, implementation risks, permissions, privacy declarations, registration materials, filing, review, and release steps.

It is designed to replace serial “what do I do next?” prompting with one maintained project ledger and a prioritized gap report.

## What it audits

- product scope, claims, monetization, and success criteria;
- prototype-to-code visual fidelity;
- personalization, data sources, defaults, caching, and fallbacks;
- build output, `miniprogramRoot`, syntax compatibility, package size, and AppID;
- physical-device layout, permissions, persistence, and image exports;
- subject eligibility, service categories, qualifications, and payment constraints;
- privacy guide, collected-information declarations, filing, review, and publication;
- production smoke tests, hotfix readiness, and post-launch learning.

## Install for Codex

```bash
git clone https://github.com/windieicloudie/wechat-miniapp-launch-skill.git \
  ~/.codex/skills/wechat-miniapp-launch
```

Then start a new session and ask:

```text
Use $wechat-miniapp-launch to audit what my WeChat Mini Program is missing and guide it to production.
```

Tools that support compatible `SKILL.md` packages can import this repository using their own skill directory conventions.

## Core behavior

- Inspect before asking.
- Track `known`, `verified`, `missing`, `blocked`, `later`, and `not applicable`.
- Prioritize P0 launch blockers, P1 material risks, and P2 improvements.
- Give evidence, impact, exact action, owner, and verification for every gap.
- Provide paste-ready platform copy and precise console paths when useful.
- Treat local build, preview, upload, experience version, review, approval, and publication as separate milestones.

See [SKILL.md](SKILL.md) for the full operating rules and [references/pitfalls.md](references/pitfalls.md) for real failure patterns.

## License

[MIT](LICENSE)
