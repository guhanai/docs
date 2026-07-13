# Guhan user documentation

Mintlify-ready documentation for the Guhan app.

## Structure

```
docs.json                     Nav config for Mintlify
introduction.mdx              Landing page
quickstart.mdx                5-minute setup guide

concepts/                     13 concept pages (the "what")
  watchlist-agent.mdx
  outreach-agent.mdx
  prospects-and-companies.mdx
  lists.mdx
  signals.mdx
  icp-scoring.mdx
  prospect-pipeline.mdx
  sender-accounts.mdx
  sequences.mdx
  personalization.mdx
  sending-safety.mdx
  inbox-tasks.mdx
  meetings.mdx
  ask-guhan.mdx
  plans-and-credits.mdx
  roles-and-permissions.mdx
  workspace-modes.mdx

guides/                       14 how-to guides (the "how")
  how-guhan-works.mdx
  onboarding-walkthrough.mdx
  connect-linkedin.mdx
  connect-email.mdx
  brand-and-voice.mdx
  create-watchlist-agent.mdx
  configure-icp.mdx
  pick-signals.mdx
  review-prospects.mdx
  create-outreach-agent.mdx
  build-sequence.mdx
  write-message-templates.mdx
  launch-outreach.mdx
  handle-replies-inbox.mdx
  schedule-meetings.mdx
  ai-reply-drafts.mdx

reference/                    5 reference pages
  keyboard-shortcuts.mdx
  signal-catalog.mdx
  faq.mdx
  troubleshooting.mdx
  glossary.mdx

images/                       (empty — add screenshots + product visuals here)
```

## How to publish

Copy the entire contents of this folder into your `guhanai/docs` GitHub repo:

```bash
cp -r docs-mintlify/* /path/to/guhanai-docs/
cd /path/to/guhanai-docs
git add .
git commit -m "docs: user-facing documentation set"
git push
```

Mintlify picks up the changes automatically on push and rebuilds.

## Assumptions in the current draft

Some things need to be verified before shipping:
- Contact email `hello@guhan.ai` — confirm this is the right support address
- Domain `guhan.ai` used in code examples — verify canonical
- Screenshot slots throughout — add real screenshots via the `images/` folder
- The 10 default message templates listed in `guides/write-message-templates.mdx` and `guides/brand-and-voice.mdx` — verify names match production
- Signal names + parameter defaults in `reference/signal-catalog.mdx` and `concepts/signals.mdx` — verify against the current signal registry

## Style guide followed

- Direct, no-fluff prose (matching Eswara's tone in the app)
- "You" and "your" throughout (user-facing)
- Concrete examples over abstract explanations
- Every concept page ends with 2-4 related-link cards
- No developer-facing jargon (`postgres`, `webhook`, `Prisma`, etc.)
- Mintlify components used: Card, CardGroup, AccordionGroup, Accordion, Steps, Step, Note, Tip, Warning, Info

## Missing / to-add

Consider adding:
- `guides/whatsapp.mdx` — WhatsApp-specific setup (currently folded into concept + connect pages)
- `reference/api.mdx` — if there's a public API surface
- `changelog.mdx` — product changelog if you want it in-docs
- `guides/team-setup.mdx` — inviting teammates, delegating senders
