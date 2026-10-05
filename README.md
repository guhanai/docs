# Guhan user documentation

Mintlify source for the public Guhan docs (docs.guhan.ai). Mintlify rebuilds on every push to the default branch.

## Structure

Navigation order follows the customer journey: set up Brand & Voice, find prospects, run campaigns, handle replies, book meetings.

```
docs.json                       Nav, redirects, SEO
introduction.mdx                Landing page
quickstart.mdx                  First-run setup
ask-guhan.mdx                   Ask Guhan chat

get-started/                    How Guhan works + sender accounts (LinkedIn / Email / WhatsApp)
brand-and-voice/                Brand + Voice, Templates, Products
audience/                       Lists, signals, how prospects land, review, Prospects, Companies, enrichment
campaigns/                      Overview, build a campaign, personalization, launch and manage, sending safety
inbox/                          Inbox, handling replies, AI reply drafts
meetings/                       Meetings + calendar integrations
workspace-settings/             Settings, plans and credits, roles, Do Not Contact, API and MCP
help/                           FAQ, troubleshooting, shortcuts, glossary
```

## Canonical pages

State each fact once and link to it from everywhere else. Do not copy these into other pages.

| Fact | Canonical page |
|---|---|
| Plans, credit costs, packs, read-only mode | `workspace-settings/plans-and-credits.mdx` |
| Send limits, send window, pacing, invite withdrawal | `campaigns/sending-safety.mdx` |
| Roles and permissions | `workspace-settings/roles-and-permissions.mdx` |
| Do Not Contact | `workspace-settings/do-not-contact.mdx` |
| Signal options | `audience/lists/signal-catalog.mdx` |
| Starter templates | `brand-and-voice/templates.mdx` |

## Source of truth

The app repo is the source of truth, in this order: code under `src/`, then `docs/features/*.md`, then these docs. When a user-facing page and the code disagree, the code wins.

| User docs area | Feature docs (app repo `docs/features/`) |
|---|---|
| get-started, sender accounts | `sender-accounts.md`, `onboarding-wizard.md`, `rate-limits.md` |
| brand-and-voice | `brand-voice.md`, `message-templates.md`, `products.md` |
| audience | `lists.md`, `lists-signal-sources.md`, `prospects.md`, `companies.md`, `pipeline.md`, `enrichment-jobs.md`, `enrichment-policy.md`, `technographs.md` |
| campaigns | `campaigns.md`, `guided-view.md`, `rate-limits.md`, `safety-layer.md` |
| inbox, meetings | `inbox.md`, `conversations.md`, `meetings.md`, `calendars.md` |
| ask-guhan | `ask-guhan.md`, `whatsapp-agent.md` |
| workspace-settings | `wallet.md`, `workspaces.md`, `orgs-and-rbac.md`, `dnc.md`, `public-api-and-mcp.md` |

When a feature doc changes behavior a customer can see, update the matching page here in the same release.

## Writing rules

- Plain, direct prose. Second person ("you").
- Say what the customer sees and can do, not how it is built. No internal stage names, enum values, or database terms.
- No vendor or data-provider names. No "webhook" unless quoting a third-party screen.
- Say "Campaign", never "agent", for the outreach unit. Retired terms (Outreach Agents, Watchlist Agents) appear only in `docs.json` redirects.
- No benchmarks, reply-rate claims, or timing promises you cannot source. Do not state a number unless you checked it in code.
- Every page has `title` and `description` frontmatter. End concept pages with 2 to 4 related cards.
- Screenshot slots are `{/* SCREENSHOT: slug — what to show */}` comments. Search for `SCREENSHOT:` to list the shots still to capture.

## Before merging

- Run a link check: every internal link must resolve to a page that exists.
- Grep for vendor names and retired terms.
- Add a redirect in `docs.json` for any page you move or delete.
