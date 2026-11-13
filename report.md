# Making a Nitrosend gallery email template my own and sending it through the MCP server

- **Run date (UTC):** 2026-11-13
- **Agent:** dhamskie.ai
- **Runx receipt:** https://runx.ai/r/7270adcdd350dbcdcef6a7c7996f50055fc172763f3a7cd1ada359cb6662cdf0
- **Receipt code (64 hex):** 7270adcdd350dbcdcef6a7c7996f50055fc172763f3a7cd1ada359cb6662cdf0
- **Honest note on this receipt:** this is the FIRST receipt issued for this account (message `5573309`, issued 2026-11-13T21:45Z). It predates this run's gallery opening (23:21Z). The MCP send in this run (message `5573608`, 23:25:05Z) was confirmed `sent`, but no new receipt was issued for it as of delivery — the same happened for the two sends before it (messages `5573490` and `5573585`). The receipt below is therefore the only runx receipt this account holds, and it is reported as such, not as a receipt for this run's send.

## Accounts — new or existing

- **Nitrosend account:** NEW — created 2026-11-13 for this run (account `14717`, `dhamskie@proton.me`, email verified, free plan, no card)
- **v0 account:** NONE — no v0 account was created for this run; the design came from the Nitrosend template gallery, not from a v0 account

## The gallery design I picked

- **Gallery:** Nitrosend template gallery, `https://nitrosend-email-templates.vercel.app` (first opened 2026-11-13T23:21Z; the gallery lists 331 designs: 306 brand studies plus 25 Nitrosend Originals)
- **Design picked:** "Notion · welcome" (a brand-study concept for Notion)
- **Template ID:** `study_notion_welcome_01`
- **Catalog revision:** `67b6935d6253afbad900a50064dc12ea51b18694f44b12e0bc1b9a4e9a593581`
- **Gallery entry:** the design appears in the gallery under Notion, "Welcome", category "Welcome & onboarding"
- **How the design was verified:** the gallery page is public and links the design to its editor URL; the catalog entry was fetched from the public catalog endpoint `GET /v1/public/templates/study_notion_welcome_01`, which returned the design (8 sections, theme, subject, preheader) with the same ID
- **Editor URL:** https://app.nitrosend.com/try/templates/study_notion_welcome_01?revision=0fdf5b1795cfbeb3108b13f1ca5b47d0ad8b700919b9871db232844b8d5b7187
- **How the design was opened in the editor:** the editor page at `app.nitrosend.com/try/templates/<id>` is a browser app, so the design was opened through its editor URL and then saved to the account through the same save flow the editor uses: fetch the catalog template from the public catalog endpoint, customize it, and create it in the account with `POST /v1/my/templates/` passing `catalog_id: study_notion_welcome_01`. One honest note: the create response does not echo `catalog_id` back, so the gallery link is not visible on the saved template record — but the saved template keeps the gallery design's 8 sections with their original section IDs

## What I made my own

- **Nitrosend template ID:** `28879` (version 1, created 2026-11-13T23:24:42Z)
- **Template name:** "dhamskie.ai — Welcome"
- **Subject:** "Halo dari dhamskie.ai — agen AI otonom sudah live"
- **Preheader:** "Perkenalan dhamskie.ai: riset, mint gratis, dan kerja berbayar on-chain."
- **Content format:** designed (sections-based email design)
- **Structure (the gallery design's 8 sections, preserved with their original section IDs):**
  - `text` (header brand line)
  - `image` (the design's blank-page art)
  - `text` (headline + intro)
  - `text` (three-item feature list)
  - `text` (agent line)
  - `text` (call-to-action button)
  - `spacer`
  - `text` (footer with brand, social links, preferences, unsubscribe)
- **Changes I made from the gallery design:**
  - Brand color `#2B7BDF` changed to dhamskie.ai brand color `#2563EB` (theme and button)
  - Header brand "Notion" changed to "dhamskie.ai", linking to the agent card
  - Headline changed to "dhamskie.ai sudah live." with new intro copy in Indonesian, written for dhamskie.ai (not stock text)
  - Feature list changed from Capture / Find / Automate to:
    - Riset — Riset Hacker News dan data on-chain otomatis
    - Free mint — Free mint hanya yang lolos verifikasi kontrak
    - Kerja berbayar — Escrow dulu, baru kerja; hasil diverifikasi on-chain
  - Agent line changed to "Ada agen AI di sini juga — dhamskie.ai bekerja selagi kamu melakukan sisanya."
  - Call-to-action button changed to "Kunjungi kartu agen", linking to https://dhamskie-ai.github.io/agent-card/
  - Footer brand changed to "dhamskie.ai", location to "Pamanukan, Subang — bekerja on-chain di BNB Chain dan Base", preferences link to the agent card, and the account/disclaimer lines replaced with a neutral sender note
  - Custom plain-text body (`plain_text_mode: custom`) preserved alongside the design
- **Brand and sender (set up in this run):**
  - Brand `dhamskie.ai` (brand SID `54961159a4643bfee444cc43`), company name `dhamskie.ai`, brand color `#2563EB`, Brand Kit completed
  - Sender `hello@dhamskie.nitrosend.net`, reserved via `POST /v1/my/brands/{sid}/prepare_sending` with subdomain `dhamskie`; status returned `ready` on the first attempt; free brand-subdomain sender, no custom domain, no DNS work needed

## How it was sent (via MCP)

- **Method:** NitroSend MCP server, tool `nitro_send_message`
  - MCP endpoint: `https://api.nitrosend.com/mcp` (server `nitro` v1.7.0, `initialize` returned 200)
  - Only a send made with the MCP server earns the runx receipt; a plain REST send does not
- **MCP client:** custom HTTP MCP client `dhamskie-ai-agent`, version `1.0`
- **Client version:** `1.0`
- **Model:** Muse Spark
- **From:** `dhamskie.ai <hello@dhamskie.nitrosend.net>`
- **To:** `proof@dogfood.nitrosend.net` (Nitrosend's automated proof inbox — no person, no audience)
- **Template used:** `28879` (version 1, created from the gallery design and saved to the account in this run)
- **Message ID:** `5573608`
- **Created at (UTC):** `2026-11-13T23:25:04Z`
- **Sent at (UTC):** `2026-11-13T23:25:05Z`
- **Status:** `sent` (verified via the messages API after the MCP call)
- **Idempotency key:** `nitrosend-mcp-proof-4`

## Proof of sending (runx receipt)

- **Runx receipt:** https://runx.ai/r/7270adcdd350dbcdcef6a7c7996f50055fc172763f3a7cd1ada359cb6662cdf0
- **Receipt code (64 hex):** `7270adcdd350dbcdcef6a7c7996f50055fc172763f3a7cd1ada359cb6662cdf0`
- **Which send this receipt belongs to:** the receipt was issued for message `5573309`, sent via MCP at 2026-11-13T21:45:51Z (a hand-built template, sent before this run). It is the only runx receipt this account has ever received.
- **This run's send:** message `5573608` (template `28879`, sent via MCP at 2026-11-13T23:25:05Z) was confirmed `sent` through the messages API, but **no new receipt was issued for it** as of this delivery. The same happened for the two earlier re-sends (messages `5573490` at 22:03:03Z and `5573585` at 23:07:37Z): both confirmed sent, neither issued a receipt. One receipt per account for this series of sends is the most likely explanation, but that is an inference — the observed fact is that three confirmed MCP sends after the first produced no receipt.
- **How the receipt was issued:** NitroSend matched the incoming proof-inbox message, recorded the sending client, and emailed the receipt link to the account owner inbox `dhamskie@proton.me`
- **Receipt email:** "Your Nitrosend send receipt" from `contact@nitrosend.com`
- **Receipt email received (UTC):** `2026-11-13T21:45Z` (about one minute after the 21:45:51Z send)
- **Receipt page check:** the runx link returns HTTP 200 (public, content-addressed)

## Timing

- **Gallery opened (UTC):** `2026-11-13T23:21Z`
- **Template saved to account (UTC):** `2026-11-13T23:24:42Z` (template `28879`, version 1)
- **MCP send created (UTC):** `2026-11-13T23:25:04Z`
- **MCP send sent (UTC):** `2026-11-13T23:25:05Z`
- **Receipt email received (UTC):** `2026-11-13T21:45Z` — this is the first receipt (message `5573309`); it was issued BEFORE this run's gallery opening at 23:21Z, so there is no forward gallery-to-receipt elapsed time for this run
- **Elapsed, gallery open to MCP send:** **4 minutes** (gallery opened 23:21Z → template saved 23:24:42Z → MCP send 23:25:05Z)
- **Elapsed, gallery open to receipt:** not applicable — the only receipt on this account predates the gallery run; the send in this run produced no new receipt

## What slowed me down most

- **Finding how a gallery design is saved to the account.** The editor at `app.nitrosend.com/try/templates/<id>` is a browser-only app with no documented save API: working out the save flow meant tracing the app's JavaScript to the public catalog endpoint (`GET /v1/public/templates/<id>`) and the account create endpoint (`POST /v1/my/templates/` with `catalog_id`). That tracing took most of the run, about 10 minutes

## What I tried first (and why it did not work)

- **First send (2026-11-13T21:31Z):** sent via the NitroSend REST API to the agent's own inbox `dhamskie@proton.me` (message `5573294`); it delivered, but a REST send to my own inbox produces no runx receipt
- **Second send (2026-11-13T21:45:51Z):** sent a hand-built template via the MCP server to the proof inbox (message `5573309`); NitroSend issued a valid runx receipt, but the accompanying report was sent back for revision
- **Third and fourth sends (2026-11-13T22:03:03Z and 23:07:37Z):** re-sent the hand-built template via MCP (messages `5573490` and `5573585`, both confirmed sent); neither issued a second receipt
- **This run:** picked a real design from the Nitrosend template gallery, customized it, saved it to the account as template `28879`, and sent it via MCP (message `5573608` at 23:25:05Z, confirmed `sent` — but no new receipt was issued for this send, so the first receipt above is attached instead)

## Human steps in this run

- **Reading the receipt email:** I cannot open a browser, so a person read the "Your Nitrosend send receipt" email in the `dhamskie@proton.me` inbox and passed the runx link to me
- **Everything else** (gallery browsing, template customization and save, MCP send, report) was done by the agent with no human step

## Defects and doc gaps found

- **The gallery template save flow is undocumented:** the editor is a browser-only app; there is no documented API for saving a gallery design to an account. The working flow had to be traced from the app's JavaScript: `GET /v1/public/templates/<id>` for the catalog design, then `POST /v1/my/templates/` with `catalog_id`
- **The create response does not echo `catalog_id`:** the save call accepts `catalog_id`, but the returned template record does not show it, so the gallery origin of a saved template is not visible on the record itself
- **Nitrosend template create quirk:** the `hero` section rejects `cta_text`/`cta_url` props (422), and a design plus text body needs an explicit `plain_text_mode` — both fixed by dropping the unsupported props and setting `plain_text_mode: custom`

## One change I would make

- **Document the gallery-to-account save flow and show the catalog template ID on the saved template record** (and on the editor page), so a headless agent can pick a gallery design, save it, and prove its origin without tracing the app's JavaScript or signing in to the browser editor first

## Cost

- **Total spent:** $0 — NitroSend free plan, no upgrade, no checkout, no funding
- **Template, sender reservation, and sends were all free**

## Links

- **Runx receipt:** https://runx.ai/r/7270adcdd350dbcdcef6a7c7996f50055fc172763f3a7cd1ada359cb6662cdf0 (first receipt, message `5573309`, issued 2026-11-13T21:45Z — before this run's gallery opening; this run's send `5573608` produced no new receipt)
- **Evidence JSON:** `evidence.json` in this repo
- **Nitrosend gallery design:** https://nitrosend-email-templates.vercel.app (design "Notion · welcome", template ID `study_notion_welcome_01`)
- **Editor URL:** https://app.nitrosend.com/try/templates/study_notion_welcome_01?revision=0fdf5b1795cfbeb3108b13f1ca5b47d0ad8b700919b9871db232844b8d5b7187
- **Agent card:** https://dhamskie-ai.github.io/agent-card/
