# Researching on regards

regards.design is a hand-picked index of real website sections (heroes, navigation, feature grids,
lists, pricing, footers), each screenshotted and read for its layout, type, colour, imagery, texture,
motion and novelty, from 1 (template) to 5 (experimental). This file is how to search it for one brief,
judge what comes back, and turn five to eight sections into a direction that looks like none of them.

## Contents

1. The tools
2. Briefing a search
3. Recipes by pass
4. Judging a hit
5. The specimen sheet
6. Mutation moves
7. The never-copy test
8. Worked example
9. Real searches, good and bad

## 1. The tools

| Tool | Use |
| --- | --- |
| `search_sections` | Find sections. `q` is a brief in plain words; `contains` filters to sections that visibly say a phrase; `roles`, `sites`, `page` filter; `categories` and `exclude_categories` (where listed) keep to or leave out kinds of site; `like` adds lookalikes of keys; `mode: "deep"` is the more careful search for a brief: about half a minute and one credit, none if it fails. |
| `view_section` | See a section's pixels. `context_px` adds the sections around it; `from_px`/`to_px` zoom into part of it. Free. Use it on every hit you might keep. |
| `get_section` | A section's visible text with sizes and positions, its page, the other sections on that page. Free. |
| `page_sections` | A whole page top to bottom: its order and rhythm. Free. |
| `similar_sections` | Sections from any site that look and read like keys you liked; `q` steers with what you want ("like these but light"), not what to leave out; the same kinds of site as your searches. |

Keys look like `standards/10` (page/section). Each hit carries `links.app` (its page on regards.design)
and `links.live` (the live page near the section). Pass a search's `searchId` as `search_id` to the
tools you use on its results.

## 2. Briefing a search

Brief it the way you would brief a designer: the kind of section, the look and feeling, what it must
show, what to avoid. A few words to a paragraph.

- With Instant, several short searches from different angles find more than one long one. For a
  component, one Deep search with its whole brief beats both.
- Describe the product, never name it: a name regards doesn't hold is read as a site to look like.
- Describe the look and structure, not the section's usual name: "a catalogue index as a table", not
  "product grid"; "numbers set large with their units", not "stats".
- Say the light you want as well as the dark you don't: "white page, light mode, not dark".
- Name a site to anchor a direction: "navigation like stripe.com but warmer".
- Ask for novelty in words: "experimental", "unusual", "conventional".
- Quotes do not filter. For sections that literally show a phrase, use `contains`; it matches small
  print too, so keep it for words a section is about.
- `understood` in the result says how your query was read. If it read in the wrong kind of section,
  repeat it with `ignore: ["roles"]`.
- Search the inventory, not the category. The category is what every competitor already looks like.
- A kind of site the user asks for ("only SaaS and AI products, no agencies or portfolios") is not that
  category: it is a filter that holds for every search. Set `categories` and `exclude_categories` where
  the tools list them, and check each hit's `category`.
- A whole brief, as an agent hands it over, is worth a Deep search: "We're designing <what, for whom>.
  Find detailed sections we can use as inspiration for this section: <the brief>".

## 3. Recipes by pass

**Mood (two or three searches).** The feeling, from different angles.

- "warm, tactile, print and packaging feel, real photography of the place"
- "quiet, architectural, lots of white, one photograph per screen"
- "loud, flat colour fields as chapters, huge type"
- "editorial, monochrome, footnotes and marginalia"

**Components (one per claim in your argument, plus detail).**

- Hero: "the name at full width, cropped by the edge", "hero that is one archival photograph and a small line of text"
- Lists and menus: "price list set like a printed label", "a catalogue index as a table, not cards"
- Proof: "numbers set large, measured, with the unit as part of the design"
- Booking or action: "a booking section that feels like a ticket"
- Footer: "footer that closes the page with the name at full width"
- Detail: "interesting line work", "experimental borders and frames", "numbers and ticks that measure something real", "a chart drawn like a scientific plate"

**Widen and drift.**

- `similar_sections` with the two or three keys you liked best, steered with `q` when needed.
- One oblique search: a word from the subject's world that is not about websites ("a 1903 postcard",
  "a train timetable", "seed catalogue", "film credits").
- An empty `q` browses the most distinctive sections in the index; add `roles` to browse one kind.

## 4. Judging a hit

Open it with `view_section` before you decide anything. Then ask:

- **Is there one thing here I can name?** A component, a treatment, a proportion. If you can only say
  "it's nice", move on.
- **Can it carry something from my inventory?** If it cannot become something for this subject, it is
  decoration.
- **Is it the craft I need?** Look at the type, spacing and edges at full size (`from_px`/`to_px`).
  A good idea set badly teaches the wrong thing.
- **Is it the category?** If it looks like what every competitor already has, it will pull the page
  back to the average.

Reject most hits. Keeping eight mediocre references is worse than keeping five good ones.

## 5. The specimen sheet

Write it in `.taste-skill/references.md`, one block per reference, then the direction under it.

```
<key> · <links.app> · live: <links.live>
takes:   <one component, named so precisely someone could find it from the words alone>
leaves:  <what you will not take: its typeface, its colours, its layout, its copy>
becomes: <what it turns into for this subject, from the inventory>
```

Good:

```
takes:   ledger rows: an eight-column catalogue table, hairline rules, tiny entries, no cards
becomes: the roast log as the menu: batch, origin, roast date, first crack, price, one row per coffee
```

Bad:

```
takes:   clean minimal layout
becomes: our layout
```

Then the direction, one line each: idea sentence; hero (specimen); each section in argument order
(specimen); type; palette; motion; the signature detail.

For a reference board the user will read (many references per section, often gathered by subagents),
one caption per reference does the same job in two sentences: "Take <the component, named precisely>.
For <the product>, <what it becomes>."

## 6. Mutation moves

A reference becomes yours when you move it. Use at least one move per specimen.

- **Material shift:** the component keeps its form and changes what it is made of. Kerning ticks become
  temperature readings; a growth curve becomes a roast curve.
- **Transpose:** move a treatment to a section it was never in. A footer's measured wordmark becomes the hero.
- **Scale:** blow a small detail up into structure, or shrink a hero device into a running detail.
- **Constrain:** one colour, one weight, one face, applied to something that had many.
- **Invert:** dark for light, negative space for content, the list as the hero and the picture as the footnote.
- **Misuse:** a component doing a different job. A table of contents as navigation; a receipt as pricing.
- **Combine:** the structure from one reference, the treatment from another, the content from the subject.

## 7. The never-copy test

- No section reproduced whole. No layout cloned, no copy, logos, illustrations, photographs or marks.
- No typeface taken unless it is free to use; otherwise find a free face of the same class.
- In step 8, set each finished section beside its reference. If a visitor could mistake one for the
  other, mutate further.
- Credit stays in `.taste-skill/references.md` and the report. Designers do not caption their
  inspirations on a client's page; pictures found with `assets.mjs` are credited on the page as usual.

## 8. Worked example

The format, shown on a made-up brief. Your references will be different: search for your own, and do
not reuse these.

Brief: Halde, a seed library in Ghent. It lends seeds in spring and asks for seeds back after the
harvest. 340 varieties, most of them local. Open Saturdays.

Searches, in order:

1. "community archive or library, warm, paper and handwriting, real photographs" (mood)
2. "a catalogue or index set like a filing system, not cards" (component)
3. "editorial, footnotes and marginalia, small notes beside the text" (detail)
4. "seed catalogue" (oblique)

Specimens kept (two of five shown):

```
profound/08 · https://www.regards.design/sections/profound/08
takes:   sheets of graph paper with binder holes, filed behind angled folder tabs
leaves:  the dark ground, the generative squares, the product copy
becomes: the seed drawers: one tab per season, one sheet per variety, the real packet scan on each

design-threads/02 · https://www.regards.design/sections/design-threads/02
takes:   book-style footnotes, a small numbered note set beside the paragraph it belongs to
leaves:  the three-column intro, the monospace labels
becomes: every variety's lender as a footnote: who brought it back, which year, from which garden
```

Earned exception: `numbering`, because the footnote numbers point at real notes and the library's
accession numbers are real.

Idea sentence: On this page, **the seeds that come back** become **a catalogue that annotates itself**.

## 9. Real searches, good and bad

From a real job in October 2026: section references for the homepage of an edge-AI product (a small
computer that runs open models in stores and warehouses, with cameras, kiosks and payment terminals
around it). The client asked for SaaS, AI and hardware-product sites only, white mode. The client's
name is left out here, as it should be in the queries. Seven subagents briefed this way ran 60 Deep
searches and 4 Instant ones and kept 178 references. An agent without the brief form, on an earlier day,
ran 1 Deep search out of 14.

**Section briefs that worked (Deep):**

```
We're designing the homepage for an edge-AI company: one hardware and software stack (a small edge
computer plus endpoints like cameras, kiosks, tablets, smart glasses and payment terminals) that lets
AI agents work on site in stores, restaurants and warehouses. Find detailed sections we can use as
inspiration for this section: "Seven vendors, or one stack." Today a payment terminal, POS, register,
tablet, camera, kiosk and wearables each come from a different vendor with its own hardware, SDK and
API. We replace them with one hardware platform and one SDK. We want many separate logos, devices or
tools converging into one hub, hub-and-spoke diagrams, or a before/after comparison of fragmented
tools against one platform. Only from SaaS, AI and product company websites, not design studios,
agencies, portfolios or fashion. White mode only.
```

```
We're designing the homepage for an edge-AI hardware and software company. Find detailed sections we
can use as inspiration for this section: model tuning, "Describe the task. Our agents tune the model."
The customer brings the task, data and acceptance goals; a chain of agents (guide, label,
post-training, training and inference) handles distillation, quantization and on-device retesting. We
want an agent workflow or pipeline diagram, numbered stages, agent cards passing work along, and the
progress UI of a training or evaluation run. Only from SaaS, AI and developer-platform websites, not
design studios, agencies, portfolios or fashion. White mode only.
```

A detail brief works the same way: "...Find detailed sections we can use as inspiration for this
detail: minimal pill buttons with a subtle inner highlight, soft bevel and soft shadow, tactile buttons
on a white page."

**Specimens it found, as board captions:**

```
adaline/05      Take the floating run window: numbered steps with RUNNING and QUEUED pills, thin
                progress bars, before-and-after cost and latency bars. For the product, the tuning
                run: guide, label, post-train, then retest on the box.
blindpay/01     Take three white status chips (tick, tick, spinner) joined by dotted connectors that
                fan into one tabbed code card. For the product, semi-integrated payments: send the
                sale, card tapped, approved, then the one request behind it.
pencil/06       Take the soft-bevelled dial: a raised disc with an inner highlight inside a tick ring,
                a big number in the middle. For the product, a 400 TOPS gauge beside the spec sheet.
voidzero/00     Take the small mono pill tags joined to an exploded stack by dotted leader lines, the
                active one filled dark. For the product, callouts pointing at parts of the box photo.
```

**What went wrong:**

- Studio, fashion, furniture and car sites were kept for their look. The client rejected every one:
  the kinds of site they asked for are a filter (section 2).
- `"status"` in a query brought back footers. "A live status chip with a dot and a count beside a
  headline" brought back status chips.
- `contains: "paid"` matched "Paid search" in footnotes.
- `similar_sections` with `q: "exploded isometric stacks, architecture diagrams"` applied
  `avoid: ["dark", "isometric"]` and left out the very thing asked for.
- An early Deep answer (`understood: null`, "first results") was judged as final and was full of
  portfolios and shops. The same search again gave the real results.
- Searches with "avoid dark" still returned dark sections: about four in ten candidates had to be
  dropped by looking.
- 16 Deep searches started in the same minute across subagents; that minute had all of the failures.
