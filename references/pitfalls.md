# Failure patterns and prevention

Use this reference as a pre-milestone audit, not as a substitute for testing.

## Product and design

### Approved demo was not reproduced

Symptoms: background becomes whiter, serif typography disappears, semantic color blocks vanish or shrink, spacing changes, and the implementation feels cheaper than the approved demo.

Prevention: freeze approved screenshots and tokens; compare implementation screenshots at matching dimensions; treat every visible delta as a defect until the user approves it.

### Layout works in simulator but not on phone

Symptoms: content requires an unnecessary scroll, bottom buttons are unreachable, labels wrap, overlays collide, or safe areas hide controls.

Prevention: test small physical screens, keyboard-open states, `100vh`/safe-area interactions, scroll containers, fixed navigation, and text expansion. Never disable scrolling before proving all required actions remain reachable.

### Personalization is cosmetic

Symptoms: editing profile data does not change results, or personalization collapses a varied calendar into nearly the same recommendation every day.

Prevention: separate daily signal from profile weighting, measure output diversity, test multiple profiles/months, document defaults, and verify changes on the experience version.

## Build and runtime

### Unsupported JavaScript syntax

Symptom: preview fails on syntax such as optional chaining (`profile?.birthDate`).

Prevention: align emitted syntax with Developer Tools settings and base library; enable appropriate compilation or use compatible syntax; inspect the generated package.

### Editing source without rebuilding

Symptom: Developer Tools displays stale behavior even though source changed.

Prevention: know the relationship between source, build output, and `miniprogramRoot`; rebuild and confirm output timestamps/content before preview or upload.

### Wrong AppID

Symptom: upload targets a test account, old organization, or another Mini Program; the formal console shows no new version.

Prevention: search for old AppIDs, replace project config, reopen the project, and verify the AppID in Developer Tools immediately before upload. Never share AppSecret.

## Permissions and exports

### Unauthorized location API blocks preview/upload

Symptom: errors such as `getFuzzyLocation is not authorized`.

Prevention: do not call a location API merely to show a city label. Use manual entry unless GPS is necessary; otherwise obtain interface permission, declare the use, implement denial UX, and test the formal AppID.

### Wallpaper does not save, or the saved image is cropped/oversized

Causes: canvas coordinate mismatch, device-pixel-ratio scaling, export dimensions different from CSS dimensions, drawing before resources are ready, missing album permission recovery, or only checking the preview canvas.

Prevention: define logical and pixel dimensions explicitly; use one scale transform; export the intended region; handle save permission denial/open settings; inspect the actual file from the phone album at full resolution.

## Registration and compliance

### Subject chosen without considering monetization

Symptom: a personal subject later needs payment or a restricted category.

Prevention: decide whether v1 is a free validation tool or a commercial product. Check current payment/category eligibility and migration constraints before registration. Do not use a dissolved company.

### Privacy says “not collected” while the app accepts profile data

Symptom: declaration conflicts with forms or permission APIs and review fails.

Prevention: treat local processing as processing; declare each data type and purpose; state optional fields and local-only storage; provide edit/delete and contact routes.

### Location declaration does not match implementation

Symptom: privacy guide declares GPS but code only uses text, or code calls location APIs absent from the guide.

Prevention: source-scan permission APIs immediately before submission and reconcile with the guide and interface settings.

### Risky or misleading claims

Symptoms: lifestyle guidance is described as guaranteed luck, medical benefit, financial outcome, precise fortune prediction, or another unqualified claim.

Prevention: keep product positioning and review copy accurate, probabilistic, and appropriate to the category. If the product truly provides a regulated/high-risk service, select the correct category and qualifications instead of hiding it.

## Process

### “Preview succeeded” is treated as “ready to release”

Prevention: require separate evidence for build, formal-AppID preview, experience version, privacy, filing, review, approval, and production smoke test.

### Too many instructions overwhelm a first-time publisher

Prevention: retain the master checklist internally but give one current console path, one action, expected success state, and requested screenshot/error at a time.
