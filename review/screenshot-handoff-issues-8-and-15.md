# Screenshot handoff for docs #8 and #15

Codex parent owns image capture and visual review. This file is a written handoff only. No images were created, faked, edited, or marked done.

Do not use real customer records or password values. Use authorized shop/role contexts. Keep issue #8 open until every criterion below is evidenced, including screenshot review.

Pinned app SHAs for copy: dev `d169f78abc4ac58e81b20ad2292c2a779f4284c0`, production `ef96d9f40d1b4e68aacfe9ef2fa62e9b9ea6b267`.

## Already accepted on #8 (do not redo)

- Job Types and Statuses walkthroughs shipped in docs PR #11 (`b64c23e`). Assets: `images/getting-started/settings-job-types.png` (2196x1408) and `images/getting-started/settings-statuses.png` (2196x1408).
- Navigation-rail crop is accepted in #8 comments as the live Owner/Admin clip. Path: `images/getting-started/navigation-rail.png` (400x1176). Role text still reads "Owner / Ad...". Do not recapture unless Daniel reopens that crop.

## Issue #15: Add a job drawer (replacement required)

| Item | Value |
| --- | --- |
| Path | `images/schedule-board/add-new-job-drawer.png` |
| Current file | 620x1000 PNG, 8-bit RGB (likely 1x) |
| Page | `schedule-board/add-a-job.mdx` Frame immediately after the intro, before `## Steps` |
| Surrounding copy | "You can add a job if you are an Owner / Admin, General Manager, Service Advisor, or Foreman." Alt: "Job Details drawer in add mode with the Schedule & Assignment, RO Details, and Vehicle sections" |
| Why it fails | Live drawer on the pinned SHA shows Last Name and Year **without** asterisks (`job-drawer.tsx` Field labels). This asset still marks **LAST NAME \*** and **YEAR \***. First Name stays required. Make and Model still have no individual asterisks; one of the two remains required. |
| Can an existing asset satisfy? | **No.** No other image is the add-mode Job Details drawer. `images/schedule-board/job-details.png` (480x666) is the compact modal, not the full drawer. |
| Required capture | Real add-mode Job Details drawer. Tight drawer pane (Schedule & Assignment, RO Details, Vehicle, Cancel and Save Changes). No leftover board chrome. |
| Size | 2x of the live drawer. Current 620px wide is 1x. Target about 1240px wide or the live 2x drawer width. PNG. |
| Crop | Full drawer content, including the missing asterisks on Last Name and Year. Optional Last Name / blank Year is the honest state if a fleet-style name is used. |
| TODO in page | HTML comment left in `schedule-board/add-a-job.mdx`. Do not remove it until this replacement is reviewed. |

App-repo compiled frames exist at `docs/review/745/screenshots/*-1280x800.png` on the pinned SHA. Those are fixture renders, not docs assets. Parent decides whether a live recapture is required. Do not copy them into this repository from this lane.

## Issue #15: Linked RO chain icon (new crop; overview can stay)

| Item | Value |
| --- | --- |
| Existing overview | `images/schedule-board/board-overview.png` (1800x1000) in `schedule-board.mdx`. Cards show RO digits with **no** chain icons. That is honest for unlinked/singleton jobs. It does **not** illustrate the new chain-icon copy. |
| Existing unassigned | `images/schedule-board/unassigned-panel.png` (280x708, likely 1x) also has no chain icons. Not misleading. Too narrow to show a linked pair. |
| Existing promised card | `images/schedule-board/promised-time-card.png` (544x136). No chain. Keep for promised-time. |
| Can existing assets satisfy the chain-icon sentence? | **No.** None of the current docs PNGs show `RoTicketLinkMark` (chain beside the RO, `data-card-ro-link` / `data-queue-ro-link`). |
| Required capture | Two jobs on the same repair-order ticket, each with the chain beside `#RO`. Optionally a third card that shares digits but is not linked, with no chain. Board cards and/or one Unassigned linked card. |
| Size | 2x tight crop of the cards, not a full-shop panorama unless the chain is readable. App compiled frames on the pinned SHA: `docs/review/746/screenshots/scheduled-linked-ro-cards-1280x800.png` and `unassigned-linked-ro-card-1280x800.png`. Same rule: parent-owned, not copied here. |
| Surrounding copy | New **Linked RO chain** bullet on `schedule-board.mdx`. Reusing-an-RO paragraph on `schedule-board/add-a-job.mdx`. |

Do not treat matching RO digits in `board-overview.png` as a link illustration.

## Issue #8 remaining TODOs (still open)

### My Hours

| Item | Value |
| --- | --- |
| TODO | `{/* TODO screenshot: My hours lens from a Technician account */}` in `reports/my-hours.mdx` (after the intro, before `## Pick a range`) |
| Path to add | `images/reports/my-hours.png` (suggested; none exists today) |
| Existing reports shots | `images/reports/reports-today.png` 1800x908; `images/reports/reports-scoreboard.png` 1800x908. Owner/Admin Today and Scoreboard. **Cannot** stand in for My Hours. |
| Surrounding copy | "Showing your work only". Four tiles: This week, Pay period hours, This month, On-time rate. Range select. |
| Required capture | Technician (or Foreman on My hours) authorized session. Tight Reports content pane at 2x, no leftover left-nav. Match the density of the Today/Scoreboard shots (~1800px wide class). |
| Blocker | #8 comments: wait for Franklynn invite role-cycle (`danielmallatt@gmail.com`). Do not invent a Technician on an Owner-only shop. |

### Accept an invite

| Item | Value |
| --- | --- |
| TODO | `{/* TODO screenshot: Set up your account page */}` in `users-and-access/accept-an-invite.mdx` (after the intro, before `## Set up your account`) |
| Path to add | `images/users-and-access/set-up-your-account.png` (suggested; none exists) |
| Nearby assets | `images/getting-started/sign-in.png` 960x924; `forgot-password.png` 940x700; `images/users-and-access/invite-user-dialog.png` 448x310. **None** is the invitee "Set up your account" page. |
| Surrounding copy | "You've been invited", heading "Set up your account.", Full name (optional), Create password, Confirm password, **Accept Invite**. |
| Required capture | Live invite redemption page at 2x. Leave password fields empty or masked. No real password text. |
| Blocker | Same Franklynn invite as My Hours. |

### Onboarding Shop Profile

| Item | Value |
| --- | --- |
| TODO | `{/* TODO screenshot: onboarding Shop Profile step */}` inside Step 1 of `getting-started/set-up-your-shop.mdx` |
| Path to add | `images/getting-started/onboarding-shop-profile.png` (suggested; none exists) |
| Nearby asset | `images/getting-started/settings-general.png` 2160x1164 is **Settings > General after setup**. Hours copy button there is **Apply Mon To Tue-Fri**. Onboarding uses **Use Monday's Hours Tue-Fri** and header "Setup · Step 1 of 3". **Cannot** satisfy. |
| Surrounding copy | Shop Name, Street Address, City, State, ZIP, Phone required. DBA / Legal Name optional. Hours of operation. Timezone and pay period. Continue, or "Fill required fields to continue". |
| Required capture | Real onboarding Shop Profile step at 2x, tight pane, header "Setup · Step 1 of 3". Authorized Owner / Admin new-shop context. Do not invent a shop. |

## What this lane did not do

- No image binaries added, cropped, or replaced.
- Screenshot TODOs remain until parent evidence lands.
- App fixture `tests/fixtures/docs-bayboard-llms.txt` is owned by BayBoard/bayboard-app#750 after this corpus is reviewed.
- What's New / Changelog was not touched.
