# Documentation review evidence: issues 8 and 15

Prepared September 8, 2026. Publication and Daniel's image approval remain pending.

## Screenshot provenance

The four PNGs are browser captures of current production application components rendered with synthetic fixtures, not live account screenshots or generated illustrations. No production account, role, invitation, or customer record was changed. Daniel must approve these fixture-backed captures before they replace the issue's originally planned live-context captures.

App source: `d169f78abc4ac58e81b20ad2292c2a779f4284c0`. Production reference: `ef96d9f40d1b4e68aacfe9ef2fa62e9b9ea6b267`.

Compiled CSS SHA-256: `b3c88257f6d079a0ba5b40a18834f2f73b97cd5e42d736e6310df6fbe4d46941`.

The optimized local compile completed. Its subsequent TypeScript stage failed because installed Vitest 4 differs from the manifest's Vitest 5; these captures are compile-only evidence. App PR 752 independently passed its clean CI build, typecheck, tests, and required gate.

| Image | Actual component and fixture | PNG dimensions |
| --- | --- | --- |
| `images/reports/my-hours.png` | ReportsScreen, technician My hours, populated preview clock frozen to August 15, 2026 | 2560 x 1852 |
| `images/users-and-access/accept-an-invite.png` | InviteRedemptionForm, synthetic invitation context, empty passwords | 960 x 1258 |
| `images/getting-started/onboarding-shop-profile.png` | OnboardingWizard Shop Profile, fictional shop, weekday 8 AM to 5 PM, Chicago timezone, biweekly period | 1760 x 2672 |
| `images/schedule-board/add-new-job-drawer.png` | JobDrawer add mode, one-part customer name, blank Last Name and Year | 1192 x 2000 |

All captures use 2x device scale after fonts load. Codex inspected all four PNGs: complete report panels, empty password fields, correct selected opening hours and pay period, optional Last Name and Year without asterisks, and visible form actions. Each image is embedded in a Frame with descriptive alt text. Final rendered Mintlify page wrapping remains a preview acceptance check; no nonbreaking-space workaround was added.

The existing board overview remains an accurate unlinked-job example. It does not illustrate the chain icon; the added guide text explains that icon without claiming the overview shows linked jobs.

## Text and provider checks

- Optional job fields and actual repair-order linking agree with the pinned app source.
- Today and Scoreboard explanations follow locked METRIC_INFO copy. No metrics or calculations changed.
- Onboarding Team can continue empty; How it Works lists are fixed open.
- Existing Job Types, Statuses, and accepted navigation images are retained.
- Mintlify Assistant was verified in the authenticated provider UI as Inactive, Enable assistant off. Normal docs search was observed. No setting changed.
- App PR 752 refreshes the live docs index fixture to 45 entries, including Job Types and Statuses. The fixture is the index, not page-body text.
- What's New / Changelog and docs.json are byte-for-byte unchanged from the base.

The text agent reported Mintlify 4.2.876 validate and broken-links passing before Codex's image integration. Mintlify CLI is unavailable locally, so those commands have not been rerun on the integrated head. Local final checks cover whitespace, image references, alt text, and preserved files; final Mintlify preview review remains pending.
