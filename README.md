# Terraflow notes pages

One page per prospect who says yes to a free teardown, served at `notes.terraflow.studio`.
Every page carries the findings, a free 30 minute call, and the paid AED 50 full marketing
teardown. The first one was Popeye Jetski, 11 September 2026, and it is the base for the rest.

## Making one

```
./new-teardown aroma-waxing          # copies _template into aroma-waxing-<random hex>
                                     # write it, every {{...}} has to go
./check aroma-waxing-<hex>           # refuses placeholders, dashes, jargon, wrong typeface
git add -A && git commit -m "..." && git push
```

Then the link is `https://notes.terraflow.studio/<folder>/`.

The random tail is deliberate. These pages name a real business and describe faults that cost
them money until they fix them, so the link is the credential, the same pattern as the daily
call sheet. `robots.txt` blocks everything and every page carries `noindex, nofollow`.

The repository is public because GitHub Pages needs it to be. Nothing goes in here that would
embarrass a prospect if somebody read the commit history. Evidence and screenshots stay in
`~/terraflow/outbound/teardowns/<domain>-<date>/`, never in this repo.

## What never changes

The chrome is the Terraflow brand and it is not adjusted per prospect. An earlier version of the
Popeye page mimicked the prospect's own site; that was wrong and was rebuilt. If every teardown
looks like the client it was written for, the brand never compounds.

- **Switzer** from Fontshare, nothing else, no fallback rendering.
- **Onyx `#0A0A0A`** ground, **Moon `#FAFAFA`** type, the neutral ramp for hierarchy.
- **Ocean `#0099FF`** used two or three times at most, on the number that matters and the paid
  button. Spend it anywhere else and it stops meaning anything.
- Square corners. Tight negative tracking. Generous space.
- The giant cropped nameplate, the hairline column grid, the two marquees, the iridescent bands,
  the counting figures, the scrolling wordmark at the end. All of it mirrors terraflow.studio.
- The `terraflow-brand` skill governs anything here carrying the name.

## What changes every time

Only the content between `02 Fix today` and the end of `06 The order I would do them in`, plus
the nameplate, the headline, the summary figures and the marquee lines. The template marks all
of it with `{{...}}` and a comment explaining what belongs there.

## Rules for the writing

1. **Every claim is checked against the live site on the day it goes out.** Not from a previous
   audit, not from markup when the claim is about what a person sees. The Popeye page had a
   finding retracted twice for exactly this.
2. **Findings are ordered by what they cost, worst first.** Not by how interesting they are.
3. **Say what you did and where you stopped.** "I put it in the basket and reached the checkout.
   I did not place an order." That sentence is why they believe the rest.
4. **Section 05 is not optional.** Name the thing you checked properly and found sound. A list of
   faults with no ending reads as a sales pitch, and it usually is one.
5. **No jargon and no roasting the person.** The work gets roasted, never the reader.
6. **Never promise a date you will not hit.** The Popeye teardown was promised "tomorrow" and
   arrived the day after that.

## The email that carries it

Sent through the reply engine, in the same thread, from the same cold mailbox. The send guard in
`tg-webhook` allows exactly two destinations in a draft: the cal.com link from the vault and a
`notes.terraflow.studio` page. Any other URL is refused, so a model cannot invent one.

## DNS and hosting

GitHub Pages from `master`, `/`. `notes` is four A records at GoDaddy pointing at
185.199.108-111.153, and `CNAME` in this repo pins the domain. HTTPS is enforced. If the
certificate ever stops being issued, unset and re-set the custom domain on the Pages API; that
restarts provisioning when it has silently stalled.
