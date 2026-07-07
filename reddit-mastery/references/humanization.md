# Humanization — killing the AI tells in Reddit text

Reddit users and mods are unusually good at smelling AI-written text, and NSFW/promo accounts get
extra scrutiny. Every comment and post must read like a specific human typed it fast. This reference is
the condensed anti-AI checklist. (Full theory lives in the bundled `humanizer` skill; this is the
Reddit-tuned subset.)

---

## The hard bans (these get an account clocked instantly)

1. **Em-dashes and en-dashes (— –).** The single most reliable AI tell. Replace every one with a period,
   comma, colon, or parentheses. Scan the final draft for `—`, `–`, and ` -- `. Any hit = not done.
2. **The rule of three.** "innovation, inspiration, and industry insights." AI forces ideas into triples.
   Break them up or cut one.
3. **Bold subheads and inline-header lists** inside a post body. `**User Experience:** ...` screams
   generated. Write flowing paragraphs; the only allowed structure is raw `Key: Value` metric lines.
4. **Emojis as decoration** on headings/bullets (🚀 ✅ 💡). Cut them. (Sparse emojis inside casual NSFW
   comments can be fine — decoration-emoji on structured text is the tell.)
5. **The "Great question! / Happy to help! / Let me know if..." wrapper.** Chatbot correspondence pasted
   as content. Delete the framing, keep the substance.

## The vocabulary blacklist

Never use: leverage, utilize, seamlessly, cutting-edge, innovative, delve, tapestry, testament,
underscore, showcase, vibrant, intricate, pivotal, crucial, foster, garner, elevate, "I'm excited to
announce," "It's funny how," "Here's the thing," "The irony is," "at its core," "the real question is."

## The sentence-shape tells

- **Copula avoidance:** "Gallery 825 serves as an exhibition space" → "Gallery 825 is an exhibition
  space." Prefer plain is/are/has.
- **Negative parallelism:** "It's not just X, it's Y." Overused. Say the thing directly.
- **Tailing -ing depth-padding:** "..., highlighting the community's connection to the land." Cut it.
- **Manufactured staccato drama:** "Then it changed. No warning. No mercy. Everything was different."
  A run of clipped fragments to fake tension. One short sentence for emphasis is fine; a run is a tell.
- **Aphorism formulas:** "X is the language of Y," "X becomes a trap." Replace with the concrete claim.
- **Fake-candid openers:** "Honestly?", "Look,", "Real talk" as a standalone pause before an ordinary
  point. A person being honest just says the thing.

---

## What human Reddit text actually looks like

- **Lowercase, contractions, typos left in.** "tbh", "idk", "kinda", "lol", "ngl", "fwiw", "ymmv".
  Sentence fragments. Starting a sentence with "and" or "but."
- **Specific, hard-to-fake detail.** A real number, a brand, a place, "the guy who used to work upstairs
  from my dentist." Humans hoard specifics; AI rounds them off.
- **Mixed feelings, unresolved.** "I think this is mostly good but something bugs me and I can't say why."
- **Variety in sentence length.** Short. Then a longer one that wanders a bit before it lands. AI trends
  to an even mid-length cadence.
- **Genuine asides and self-corrections.** "(I keep wanting to say 'almost' here but it really was
  certain.)"
- **One opinion, stated flatly.** React to things, don't neutrally summarize them.

---

## Voice matching (do this when the account has a persona)

If the account has past comments or a defined persona, read a sample first and match: sentence length,
casual-vs-formal level, punctuation habits, recurring tics. Don't just strip AI patterns — replace them
with that persona's patterns. If she writes short and sweary, don't produce long and polished.

Each account should have a **stable persona** (typing speed, verbosity, favorite words, topics). Keeping
personas distinct across a fleet also prevents the whole fleet reading like one author, which is its own
detection vector.

---

## The spintax trap (fleet-specific)

When reusing a comment shape across accounts, **spintax alone is not enough** — and spintax with the
**same link** across accounts will flag the whole set. Rewrite genuinely per thread, vary the link/vector,
and never let two accounts post near-identical wording. Reused wording is a spam/manipulation signal even
when the words are technically "spun."

---

## Final pass (run on every draft)

1. Read it aloud. Does it sound like a person talking, or like a press release?
2. Search for `—` `–`. Zero allowed.
3. Kill any word from the blacklist.
4. Is there one specific, hard-to-fake detail? If not, add one.
5. Is there one honest gap or opinion? If not, add one.
6. Would you say this out loud at a bar? If not, rewrite.
