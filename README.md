# regards art direction

An agent skill that makes your coding agent research real websites before it designs one.

It is a fork of [tasteskill v2](https://github.com/Leonxlnx/taste-skill) by Leonxlnx (MIT). tasteskill
deals your agent one of 20 directions distilled from 247 gallery sites. This fork keeps everything
else tasteskill does (the subject inventory, the idea and competitor tests, real pictures from open
archives, the real-browser inspector, the look-and-fix loop) and changes one step: instead of dealing
a direction, the agent searches [regards.design](https://regards.design), a hand-picked index of real
website sections searchable by look, for this brief only. It looks at the pixels, keeps five to eight
sections, names the one thing it takes from each and what that thing becomes, and derives the
direction from what it kept.

## Install

```bash
npx skills add filipwojda/regards-skill
claude mcp add --transport http regards https://mcp.regards.design/mcp
```

The second line connects the regards.design MCP server (Claude Code; other agents add the same URL in
their MCP settings). Without it the skill falls back to tasteskill's deal and says so.

## What changed from tasteskill

- Step 3 is research on regards instead of `draw.mjs`: mood searches, one search per section of the
  page's argument, a widen-and-drift pass, `view_section` on every hit it might keep, and a specimen
  sheet in `.taste-skill/references.md` (`takes / leaves / becomes` per reference).
- The direction (hero, sections, type, palette, motion, signature detail) is derived from the
  specimens, not dealt.
- Earned exceptions: tasteskill bans hairlines, monospace, index numbers and tiny tracked labels by
  its author's choice (its own study found them more common on award sites). This fork keeps the ban
  as the default and lets a viewed reference lift it, once, when the device carries real information.
- The look step adds a reference pass: each section beside the section it drew on. Took the named
  thing? Looks like none of them?
- Never copy: no section, layout, copy, picture, mark or licensed typeface taken from a reference.
- Material: colour as whole fields, printed things drawn as paper with grain from within, line work that
  carries data, at most one metal accent, every section a poster. Two narrow earned exceptions (`shadow`
  under a physical object, `palette-purple` as one of several fields) so the inspector agrees with it.

`references/regards.md` has the search recipes and the specimen format. `references/draw.md` is the
original deal, kept as the fallback.

## Requirements

Node 22+ and Chrome, Edge or Chromium for `inspect.mjs`. A regards.design account for the MCP server, on any plan, Free included.

## Credit

The study, inventory, idea tests, open-collection pictures, inspector, critique rubric and look loop
are tasteskill's, by Leonxlnx, under the MIT licence (see LICENSE). The research step is this fork's.
