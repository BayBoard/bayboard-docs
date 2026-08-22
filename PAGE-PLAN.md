# BayBoard shop help: v1 page plan

Internal planning file. Not in `docs.json`, not a public page.

Source of truth for "shipped": the `bayboard-app` repo on `dev` (read-only), the `DOCUMENTATION_CATEGORIES` help spine in `src/lib/support/documentation.ts`, `SUPPORT_CHANGELOG` in `src/lib/support/changelog.ts`, `SUPPORT_SHORTCUT_GROUPS` in `src/lib/support/shortcuts.ts`, and the live app at dev.bayboard.io. Nothing below is documented unless it exists in one of those.

Landing page paths match the in-app Documentation cards exactly: `/getting-started`, `/schedule-board`, `/team-and-roles`, `/auto-scheduler`, `/reports`, `/billing`, `/users-and-access`, `/time-off`.

Role names as the app shows them: Owner / Admin, General Manager, Service Advisor, Foreman, Technician.

## Pages

| Page | File | For | Shipped proof |
| --- | --- | --- | --- |
| Home | `index.mdx` | Everyone | Site entry. Links to the eight in-app Documentation cards plus Support and What's New. |
| Getting started (landing) | `getting-started.mdx` | Everyone | In-app card "Getting Started". |
| Set up your shop | `getting-started/set-up-your-shop.mdx` | Owner / Admin, General Manager | Onboarding wizard `src/components/onboarding/onboarding-wizard.tsx`, changelog v1.0.3. |
| Sign in and reset your password | `getting-started/sign-in.mdx` | Everyone | `/login`, `/forgot-password`, `/reset-password` forms. |
| Find your way around | `getting-started/find-your-way-around.mdx` | Everyone | App shell `src/components/shell/app-shell.tsx`, global search, focus mode. |
| Shop profile and hours | `getting-started/shop-profile-and-hours.mdx` | Owner / Admin, General Manager | Settings > General, changelog v1.0.4. |
| Notifications | `getting-started/notifications.mdx` | Everyone | Settings > Notifications `notifications-settings-section.tsx`. |
| My profile and password | `getting-started/my-profile.mdx` | Everyone | Settings > My Profile `profile-settings-section.tsx`. |
| Schedule board (landing) | `schedule-board.mdx` | Everyone | In-app card "Schedule Board", changelog v1.0.1. |
| Add a job | `schedule-board/add-a-job.mdx` | Owner / Admin, General Manager, Service Advisor, Foreman | **Add New Job** in the Unassigned panel, `job-drawer.tsx`. |
| Assign a job | `schedule-board/assign-a-job.mdx` | Same four roles | Drag and drop `board-interactions.ts`, drop validation. |
| Move or resize a job | `schedule-board/move-or-resize-a-job.mdx` | Same four roles | Drag on board, resize grip `resize.ts`. |
| Job details | `schedule-board/job-details.mdx` | Everyone (edits: four roles) | `job-detail-modal.tsx`, changelog v1.0.5. |
| Job statuses | `schedule-board/job-statuses.mdx` | Everyone | Six fixed statuses, status pill menu, Waiting on Parts modal. |
| Unassigned jobs | `schedule-board/unassigned-jobs.mdx` | Everyone | `unassigned-panel.tsx`, filters, "For" tag, bump banner. |
| Promised time | `schedule-board/promised-time.mdx` | Everyone | Promised By fields, card flag, overdue rule, Today report tile. |
| Carry Forward and Reset Day | `schedule-board/carry-forward-and-reset-day.mdx` | Owner / Admin, General Manager, Service Advisor | Top-bar icon buttons, `bulk-operations.ts`, changelog v1.0.8. |
| Search | `schedule-board/search.mdx` | Everyone | `global-search.tsx`, Ctrl+K. |
| Team and roles (landing) | `team-and-roles.mdx` | Everyone | In-app card "Team & Roles". |
| Add a technician | `team-and-roles/add-a-technician.mdx` | Owner / Admin, General Manager | Settings > Team **Add Technician**. |
| Tech capability profile | `team-and-roles/tech-capability-profile.mdx` | Owner / Admin, General Manager | Settings > Team "Tech Capability Profile" panel. |
| Archive or restore a technician | `team-and-roles/archive-a-technician.mdx` | Owner / Admin, General Manager | Settings > Team "Archived" checkbox and confirm. |
| Users and access (landing, what each role can do) | `users-and-access.mdx` | Everyone | In-app card "Users & Access", role gates in `route-access.ts`, settings tabs, board gates. |
| Invite a user | `users-and-access/invite-a-user.mdx` | Owner / Admin, General Manager | Settings > Users **Invite User** dialog, resend, revoke. |
| Accept an invite | `users-and-access/accept-an-invite.mdx` | Invited staff | `/invite` redemption form. |
| Change a role or deactivate an account | `users-and-access/change-a-role-or-deactivate.mdx` | Owner / Admin, General Manager | Settings > Users member detail. |
| Auto-Scheduler (landing) | `auto-scheduler.mdx` | Everyone | In-app card "Auto-Scheduler". |
| Run Auto-Schedule | `auto-scheduler/run-auto-schedule.mdx` | Owner / Admin, General Manager, Service Advisor | **Auto Schedule** button, confirm dialog, result toast, "Didn't fit" chips, Undo. Changelog v1.0.8. |
| Scheduling preferences | `auto-scheduler/scheduling-preferences.mdx` | Owner / Admin, General Manager | Settings > Scheduling `scheduling-settings-section.tsx`. |
| Time off (landing) | `time-off.mdx` | Everyone | In-app card "Time Off", changelog v1.0.6. |
| Add time off | `time-off/add-time-off.mdx` | Owner / Admin, General Manager, Service Advisor, Foreman | `time-off-section.tsx` add form. |
| Delete time off | `time-off/delete-time-off.mdx` | Same four roles | Delete confirm in `time-off-section.tsx`. |
| Reports (landing) | `reports.mdx` | Everyone | In-app card "Reports", changelog v1.0.7. |
| Today | `reports/today.mdx` | Owner / Admin, General Manager, Service Advisor, Foreman | `/reports/today`. |
| Scoreboard | `reports/scoreboard.mdx` | Same four roles | `/reports/scoreboard`. |
| My hours | `reports/my-hours.mdx` | Foreman, Technician | `/reports/my-hours`. |
| Export and print | `reports/export-and-print.mdx` | Owner / Admin | **Export CSV**, **Print**, `/api/reports/export`, `/reports/print`. |
| Billing | `billing.mdx` | Owner / Admin | Settings > Billing: current plan, next billing date, **Open Billing Portal** (Stripe Customer Portal). |
| Contact Support | `support/contact-support.mdx` | Everyone | `/support/contact` form on `dev` (PR 556 path): caps, types, rejection copy, "Ticket sent", mailto failsafe. |
| Keyboard shortcuts | `support/keyboard-shortcuts.mdx` | Everyone | `SUPPORT_SHORTCUT_GROUPS`, only `available: true` entries. |
| System status | `support/system-status.mdx` | Everyone | `/support/system-status`, status.bayboard.io. |
| What's new | `changelog.mdx` | Everyone | `SUPPORT_CHANGELOG` only, verbatim bullets. |

## Screenshots

Real captures from dev.bayboard.io, PNG, cropped, under `/images/<group>/`. Pages reference only these paths. Anything not captured is left as an HTML comment TODO in the page, never faked.

| File | Shows |
| --- | --- |
| `images/home/schedule-board-overview.png` | Full board with technician columns, Unassigned panel, Shop Performance strip |
| `images/getting-started/navigation-rail.png` | Left rail: Schedule, Reports, Settings, Support, account menu |
| `images/getting-started/settings-general.png` | Settings > General shop profile and Hours of Operation |
| `images/getting-started/settings-notifications.png` | Settings > Notifications toggles |
| `images/getting-started/settings-my-profile.png` | Settings > My Profile, cropped to the Change Password panel so no email address is shown |
| `images/schedule-board/board-overview.png` | Board grid with jobs, capacity chips, time column |
| `images/schedule-board/add-new-job-drawer.png` | Job Details drawer in add mode |
| `images/schedule-board/job-details.png` | Job Details modal |
| `images/schedule-board/status-menu.png` | "Set status" pill menu |
| `images/schedule-board/unassigned-panel.png` | Unassigned Jobs panel with filters and Add New Job |
| `images/schedule-board/carry-forward-dialog.png` | "Carry forward uncompleted jobs?" dialog |
| `images/schedule-board/search.png` | Global search results |
| `images/team-and-roles/settings-team.png` | Settings > Team technician detail |
| `images/team-and-roles/capability-profile.png` | Tech Capability Profile panel |
| `images/users-and-access/settings-users.png` | Settings > Users list and member detail |
| `images/users-and-access/invite-user-dialog.png` | Invite User dialog |
| `images/auto-scheduler/run-auto-schedule-dialog.png` | "Run Auto-Schedule?" confirm |
| `images/auto-scheduler/settings-scheduling.png` | Settings > Scheduling hard constraints and soft preferences |
| `images/time-off/time-off-management.png` | Time Off Management panel |
| `images/reports/reports-today.png` | Reports > Today tiles |
| `images/reports/reports-scoreboard.png` | Reports > Scoreboard |
| `images/billing/settings-billing.png` | Settings > Billing, cropped to the Current plan and Payment method cards |
| `images/support/contact-support-form.png` | Contact Support form |
| `images/support/keyboard-shortcuts.png` | Keyboard Shortcuts screen |
| `images/support/system-status.png` | System Status screen |

Not captured (left as TODO comments in the pages): onboarding wizard steps (already completed for this shop), the sign-in page (the only capture had a real email address autofilled, so it was discarded), password reset pages, the invite acceptance page, the My hours report (Foreman or Technician only), and a mid-drag drop preview.

## Skipped on purpose (not documented)

- Crisp, Loops, AutoLeap, impersonation, Danger Zone internals (no Danger Zone UI is shipped).
- In-app billing controls beyond **Open Billing Portal**: View Plans modal, Cancel Subscription, Resume, plan switcher, `/plans`, `/checkout`, trial-expired and subscription-ended gate pages. #492 and #491 stay parked.
- Auto-Scheduler propose-and-review screen (parked as a later card). Today the live board is the review.
- Ask BayBoard (Ctrl+J is marked unavailable in the app and is hidden from the shortcut list).
- Transfer Ownership flow (shipped, but owner-only and rare; not part of the v1 spine).
- Unbuilt or later cards, launch-gate checklists, maintenance page, auth-review harness, support-operator process, Storage or GCS links, internal email addresses.
- Request access / early-access lead form (not an account flow).
- Legal link (external to bayboard.io/legal).

## Ask Daniel

1. Settings > Billing on `dev` has a live **Cancel Subscription** link with a typed CANCEL confirm. The brief says no in-app Cancel. It is left out of the Billing page. Confirm it should stay undocumented, or whether it is being removed.
2. Settings > Time Off tab is visible only to Service Advisor and Foreman. Owner / Admin and General Manager add time off inside Settings > Team. Documented that way. Confirm that is intended, not a bug.
3. The product uses three spellings: the button reads **Auto Schedule**, the confirm reads "Run Auto-Schedule?", and the progress panel and shortcut list say "Auto-Scheduler". Docs use "Auto-Schedule" for the feature and quote the button as **Auto Schedule**. Say if you want one spelling in the app.
4. The Add Job drawer field "Scheduled Time" is the block length in hours, not a clock time. Docs explain it as block length. Consider relabeling in the app.
5. Keyboard shortcuts list shows both Ctrl+S "Save changes" and Ctrl+Enter "Save & close", but the drawer has one **Save Changes** button and both shortcuts do the same save. Docs list both keys as the app shows them and say both save and close.
6. The Documentation cards in the app open only when `NEXT_PUBLIC_DOCS_URL` is set in the deployment. Confirm it points at https://docs.bayboard.io in production.
7. The in-app Invite User dialog says an invite "cannot be re-sent", but the invite detail has a **Resend Invite** button. Docs describe Resend Invite as it works. Consider fixing the dialog copy.
8. Pages with TODO screenshot comments (onboarding, sign in, accept invite, My hours, drop preview) need a capture from a session that can reach them.
9. Support email failsafe is support@bayboard.io in the app. The `/shop-unavailable` page uses hello@bayboard.io. Docs mention only support@bayboard.io.
