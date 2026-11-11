# BayBoard help site threat model

This public document describes how to review changes to the help site. It records architecture and review scenarios, not security findings or deployed-control verification. Keep finding details and dispositions in an approved private record, as required by `AGENTS.md:34-56`.

## 1. Overview

The repository supplies public help for shop staff. Mintlify publishes the MDX pages, screenshots, branding, and navigation at `docs.bayboard.io`; a pull request may provide a preview, and an authorized merge to `main` publishes the site (`README.md:1-10,21-30`). The pages explain app workflows but do not implement app authentication, billing, scheduling, or support services (`docs.json:95-190`; `getting-started/sign-in.mdx:8-21`; `support/contact-support.mdx:35-75`).

| Component | Source and role |
| --- | --- |
| Site configuration | `docs.json:1-23,58-90,95-190` defines search presentation, public links, and navigation. |
| Help pages | `README.md:5-10` describes task-based MDX; `index.mdx:12-59` links visitors to guides. |
| Screenshots | `index.mdx:8-10` embeds an app capture; `README.md:30` sets image presentation conventions. |
| Publication | `README.md:21-30` describes validation, preview, and merge-to-publication. |

| Deployment or workflow | Resource or capability | Configuration and safe effective value | Readers or recipients | Enforcing control and evidence |
| --- | --- | --- | --- | --- |
| Public site | MDX, screenshots, CSS, and `docs.json` | Repository content becomes public pages at `docs.bayboard.io`; Mintlify's internal output locations were not inspected. | Visitors and search crawlers. | PR review, `mint validate`, `mint broken-links`, and authorized merge (`README.md:1-10,21-30`; `AGENTS.md:22-32`). |
| PR preview | Proposed documentation revision | Mintlify may issue a preview URL for a PR; its access settings were not verified. | Reviewers and anyone with preview access under the host's policy. | Repository review process; do not treat a preview as release verification (`README.md:21-30`; `AGENTS.md:24-32`). |
| Outbound navigation | Marketing, app, status, and legal links | Static URLs in navbar and footer. | Separate BayBoard services. | Source review and broken-link validation (`docs.json:58-90`; `README.md:21-28`). |
| Public images | App screenshots under `/images/` | MDX references the published image path. | Public readers. | Real capture with fictional or demo data required before publication (`index.mdx:8-10`; `AGENTS.md:13-20`). |

## 2. Threat model, trust boundaries, and assumptions

The important assets are the accuracy of customer instructions, integrity of public links, privacy of screenshots and text, and separation of private security records from public review. A visitor can read, search, and follow links. A contributor may propose changes only if separately granted repository access; publication requires the authorized merge. The help site does not grant app privileges through a page view (`docs.json:6-20,58-90`; `README.md:21-30`; `AGENTS.md:22-32`).

- **Contributor to public reader.** MDX wording and images cross from a proposed repository change into a customer-facing page. MDX can also contain components or embeds, and the site's styles are repository assets, so new executable or third-party content needs review as a separate publication risk (`README.md:7-10`). Claims about a feature or workflow need an approved, current app source; screenshots need real demo-data captures (`AGENTS.md:7-20,24-26`).
- **Help site to separate services.** Visitors may follow configured links to the app, status page, or legal pages. Those services enforce their own behavior; this repository controls only the published link and explanation (`docs.json:58-90`; `support/system-status.mdx:6,35-41`).
- **Review to publication.** A PR preview helps inspect a change. Validation and review precede an explicitly authorized merge to `main` (`README.md:21-30`; `AGENTS.md:22-32`). Security details remain in a private record, with only a sanitized status in public PR material (`AGENTS.md:34-56`).

Mintlify rendering, hosting headers, search internals, preview access, and branch-protection settings are outside the inspected repository. The pages describe customer-visible app behavior; they are not evidence that the app's underlying controls are currently deployed (`AGENTS.md:16-18,24-26`).

## 3. Attack surface, mitigations, and attacker stories

These are review scenarios, not confirmed findings. Priority depends on whether a proposed change is accepted and published.

| Priority | Scenario and possible effect | Prerequisite | Existing control and review action | Evidence |
| --- | --- | --- | --- | --- |
| High, conditional | Incorrect account, payment, or operational guidance leads customers to take an unsafe or costly step. | A mistaken or unauthorized claim is published. | Verify customer-visible behavior against an approved current source; inspect the preview and keep merge approval separate. | `AGENTS.md:7-18,22-32`; `docs.json:105-188` |
| Medium | A screenshot or page exposes information that should remain private. | Sensitive material enters a proposed image or text and is published. | Use real captures with fictional or demo data; review the image and rendered page. | `AGENTS.md:11-20`; `index.mdx:8-10` |
| Medium, conditional | An accepted MDX component, embed, or new script/style asset runs unwanted behavior or makes third-party requests on the public docs origin. | Requires a contributor change to be reviewed, merged, and published; the current repository has no JavaScript or TypeScript source file establishing such behavior. | Inspect any new component, script, iframe, or external asset and the rendered preview before publication. | `README.md:7-10,21-30`; `AGENTS.md:22-32` |
| Medium | A changed link sends readers to the wrong destination. | A destination change is accepted and published. | Review configured URLs and run broken-link validation before PR-ready. | `docs.json:58-90`; `README.md:21-28` |
| Medium | A public review or document reveals security details. | Sensitive detail is placed in public content or PR discussion. | Keep details in an approved private record; publish only sanitized status and use the private review channel. | `AGENTS.md:34-56` |
| Low | A typo or stale, non-consequential instruction causes confusion. | The wording is published without catching it in review. | Check against the app and follow the writing and validation conventions. | `README.md:21-30`; `AGENTS.md:24-26` |

## 4. Severity calibration

| Severity | Example for this site | Limit on the claim |
| --- | --- | --- |
| Critical | A confirmed publication that directly exposes a broad set of private customer or credential data. | A hypothetical screenshot or PR alone is not proof of public exposure. |
| High | Published false guidance that predictably causes serious customer harm, or a broad redirect of readers through a compromised public link. | Establish the published revision, audience, and actual consequence. |
| Medium | Published private information affecting a limited audience, a materially wrong workflow, or a misleading outbound link. | Confirm what was public and for how long before assigning impact. |
| Low | A minor copy or navigation defect with no meaningful privacy, security, or customer-workflow consequence. | Do not label ordinary editorial corrections as security findings. |

The publication boundary and private handling rule remain the governing controls (`AGENTS.md:22-56`). This model does not authorize a merge, publication, or disclosure of security findings.
