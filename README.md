# Terraflow notes pages

One static page per prospect, served at `notes.terraflow.studio`, styled to look like the
prospect's own site rather than ours. Each page carries the free teardown, a cal.com link for a
free 30 minute call, and the paid AED 50 full marketing teardown.

## How a page is addressed

`notes.terraflow.studio/<name>-<random hex>/`

The random suffix is deliberate. These pages name a real business and describe faults on their
live site, sometimes faults that cost them money until they fix them. The link is the credential,
same pattern as the daily call sheet. `robots.txt` disallows everything and every page carries
`noindex, nofollow`, so nothing here reaches a search result.

The repository is public because GitHub Pages needs it to be. Do not put anything in here that
would embarrass a prospect if a person went looking through the commit history.

## Adding a prospect

1. Copy an existing folder, rename it `<name>-<12 random hex>`.
2. Keep the Terraflow brand: Switzer from Fontshare, Onyx #0A0A0A ground, Moon #FAFAFA type,
   one Ocean #0099FF moment, square corners. The `terraflow-brand` skill governs it.
3. Keep the evidence in `~/terraflow/outbound/teardowns/<domain>-<date>/`, never in here.

## DNS

`notes` CNAME -> `obitus599.github.io`, managed at GoDaddy. `CNAME` in this repo pins the domain.
