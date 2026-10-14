# The fallback: dealing a direction

Use this only when the regards tools are not connected or fail. It is tasteskill v2's original step 3,
unchanged in substance. Say in the report that the direction was dealt, not researched.

```bash
node <skill>/scripts/draw.mjs --sector <sector> --brief "<one line about the subject>" \
  --sections <roles in the order of your argument> [--tone <tone>] [--have <assets>] [--keep palette,type] \
  --options 3
```

This deals three of twenty directions and prints a short summary of each. Hold each one against your
inventory: which way of composing can carry something only this client has? Choose that one, not the
most familiar, and write one line in your notes on why. Then deal the full sheet:

```bash
node <skill>/scripts/draw.mjs <the same arguments, without --options> --direction <chosen id>
```

- `--sector`: `node <skill>/scripts/draw.mjs --list sectors`. Pick the closest.
- `--sections`: roles from `--list roles` (features, showcase, how-it-works, testimonial, proof, stats,
  pricing, faq, cta, footer, intro, about, work, gallery, list, contact). The hero is implied.
- `--tone` (optional): quiet, bold, warm, technical, playful, luxury, editorial.
- `--have`: assets that really exist: `photography`, `product-photo`, `product-ui`, `illustration`,
  `video`. Leave it out if you have none. Pictures you will find in the open collections are not the
  project's own; leave them out of `--have`.
- `--keep palette,type`: when the brand already fixes colours or typefaces.

The command prints a direction sheet. Adopt it; do not blend it with the layout you would have made
anyway. Redraw one slot (`--redraw hero | type | palette | photos | section:<role> | direction`) only
for a reason you can state, and record every redraw in your report. When a dealt section cannot hold
the real content, list the others with `--alternatives <role>` and take one with
`--redraw section:<role>=<id>`. If a dealt palette fights the subject's own material, redraw it once,
or keep its proportions and take the colours from the subject. Reprint the sheet with
`node <skill>/scripts/draw.mjs --show`.

With a dealt sheet, the rest of the run reads "the sheet's blueprint" wherever it says "your line on
the sheet", and the photographs dealt on the sheet may stand in where an honestly generic picture fits
(the sea for a sea house), never as the subject.
