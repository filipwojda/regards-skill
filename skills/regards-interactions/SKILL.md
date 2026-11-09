---
name: regards-interactions
description: Motion from real interactions with regards.design, a library of interactions recorded on live websites (hovers, clicks, focus states, scroll reveals, scroll-linked motion, loops, menu glides), each measured in the browser for its timing, curves and moving parts. Use it whenever the work is motion on the web - a hover state, a button press, a menu or navbar, tabs, a scroll reveal, a page or panel opening - when choosing an easing curve, a duration or a stagger, when matching how a named site moves ("make this feel like dub's navbar"), and when motion feels off (janky, slow, floaty, cheap). Not for layout, type or colour: the regards-design skill and search_sections do those. Needs the regards.design MCP server, https://mcp.regards.design/mcp.
---

# Motion from real interactions with regards.design

Motion made from memory comes out as the same few defaults: 300 ms, ease-in-out, a fade and an 8 px rise.
Real interfaces that feel good are more particular than that. A menu opens in 180 ms and closes in 120, a
card lifts on a curve that is nearly all start, a highlight glides from item to item on a spring that
settles once. regards.design keeps interactions like these, recorded on live sites and measured frame by
frame in the browser, so the timing you pick comes from something that works.

## When to search

- Before you write any transition, animation or keyframes for a hover, press, focus, menu, tabs, reveal,
  marquee or loop.
- When you choose an easing curve or a duration, or a stagger between items.
- When the user names a site whose motion they like, or says motion feels wrong.

Skip it for a one-line fix the user has already specified ("make it 200 ms").

## How to search

`search_interactions` takes words, filters, or both.

- **Words** (`q`): what moves, what sets it off and how it should feel. "a card hover that lifts and feels
  premium", "a navbar highlight that glides between items", "clip-path reveal on scroll", "a 60 ms stagger
  on a list", "like Stripe's bento hover but softer". Name a site when the user did.
- **Filters**, each strict: `trigger` (hover, click, focus, scroll-in, scroll-linked, loop, glide), `element`
  (card, button, nav, menu, tabs, hero…), `moves` (move, scale, fade, blur, clip, color, shadow, radius,
  morph, draw…), `feel` (ease-out, ease-in-out, spring, linear, steps…), `min_ms` and `max_ms` (the main
  move's length), `look`, `site_kind`, and `curve` (a CSS easing, a preset such as expo-out, or
  "spring(170, 18)": the main move rides within 15% of it). Several values in one filter mean any of
  them; filters together mean all.
- **Filters alone** list everything they keep, the closest to `curve` first, and `kept` says how many there
  are. Use them to see what exists ("every hover under 200 ms on a spring") before you describe one.

A search with words is one Instant search on the account's plan, shared with section searches; filters
alone count nothing. Both are paced per minute: search, read, then search again, rather than in bursts.

## How to read a result

- `beats`: the timeline. Each beat says when it starts after the trigger (`atMs`), how long it runs
  (`durationMs`), what moves, how, and its curve (`easing`). This is what you recreate.
- `measured`: what the browser saw: the main move's length (`mainMs`) and curve (`curve`, as CSS or
  `spring(stiffness, damping)`), the property families that move, a stagger (`stepMs`, `count`), whether it
  moves by transforms alone, and what draws a canvas.
- `parts`, `feel`, `why`, `handles`: what each moving part does, how it feels, why it works, and short
  names for the technique.
- `small`, `clip` and `picture`: the recording and a still at its peak. Watch the recording when you can;
  the words describe it, the recording is it.

## How to turn one into code

1. Keep the timeline: each beat becomes a transition or keyframe step with `delay` = `atMs`, duration =
   `durationMs` and the beat's easing as given. A `cubic-bezier(…)`, `steps(…)` or `linear(…)` goes into CSS
   as it is.
2. A spring (`spring(stiffness, damping)`): in Motion or Framer Motion, `{ type: "spring", stiffness, damping }`
   with mass 1; in plain CSS, a `linear()` easing sampled from it, over the measured length.
3. A stagger: each item's delay is its index times `stepMs`.
4. Transforms alone (`transformOnly`): animate `transform` and `opacity`, never layout properties, so it
   stays on the compositor.
5. Exits: when the beats show the way out, keep its own timing (they are often faster than the way in).
6. Fit it to the product: keep the timing, the curves and the order of the beats; change the sizes,
   colours and content to the user's own. Never copy a site's assets, marks or copy.
7. Respect `prefers-reduced-motion`: keep the state change, drop the travel.

## Show the user

Name what you took and from where: each interaction you used, linked to its `link` (its page on
regards.design, with the recording), and its live page (`url`) when they want to try it there.
