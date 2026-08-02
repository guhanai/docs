# Guhan user documentation

Mintlify-ready documentation for the Guhan app.

## Structure

```
docs.json                     Nav config for Mintlify
introduction.mdx              Landing page
quickstart.mdx                5-minute setup guide

agents/outreach-agents/       Outreach Agent concept + how-tos
audience/                     Lists (hub + sources + signal catalog + scoring
                              + pipeline + review-prospects), prospects, companies
brand-and-voice/              Brand + Voice + Templates + Products
inbox/                        Inbox tasks + reply handling
meetings/                     Calendar integrations + scheduling
get-started/                  Onboarding walkthrough + sender-account connect
                              (LinkedIn / Email / WhatsApp)
workspace-settings/           Plans + credits + roles + permissions
help/                         FAQ, troubleshooting, glossary, keyboard shortcuts
ask-guhan.mdx                 Ask Guhan reference

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
