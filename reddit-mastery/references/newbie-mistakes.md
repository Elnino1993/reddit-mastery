# Newbie Mistakes — the error catalog (diagnostic reference)

This is the "point at what they're doing wrong" reference. When the user describes an account, a plan, a
draft, or a problem ("my posts keep disappearing", "got banned", "no upvotes"), scan against this catalog
and name the specific mistake, why it's costing them, and the fix.

Each entry: **Symptom → Why it's wrong → Fix.** Grouped by area. The 🔴 ones are account-killers.

---

## A. Account setup & infrastructure

**🔴 Promoting on a brand-new account.** *Symptom:* dropping OF/product links or heavy promotion in the
first days. *Why:* no trust, no karma, no history — reads as pure spam, "nuked immediately." *Fix:* warm
up 14–30 days first (see warmup-playbook.md); links come last.

**🔴 Many accounts on one IP / fingerprint.** *Symptom:* running a fleet through one connection or reusing
a browser profile. *Why:* correlated accounts get **banned simultaneously**. *Fix:* one account = one
residential/mobile IP + one coherent antidetect profile.

**🔴 Cheap datacenter proxies or a commercial VPN.** *Symptom:* NordVPN/datacenter IPs. *Why:* flagged
immediately; fresh accounts on them can't even send 1–3 DMs. *Fix:* residential/mobile proxies from real
ISPs, consistent per account.

**Incoherent fingerprint.** *Symptom:* Chrome UA on a Firefox engine, impossible core counts, timezone/geo
not matching the IP. *Why:* the mismatch — not the antidetect browser itself — is what gets caught. *Fix:*
coherent fingerprint, stable from creation, derived values realistic.

**Changing password/email/IP right after acquiring an account.** *Symptom:* immediate credential or
location changes. *Why:* sudden changes trigger suspicion flags. *Fix:* space changes to Days 3–5+; change
location no more than every 2–3 days.

**Buying accounts with only post karma.** *Symptom:* high post karma, near-zero comment karma. *Why:*
signals artificial upvoting. *Fix:* prefer comment-karma-heavy accounts on disposable emails.

**Not verifying email.** *Symptom:* skipped email verification. *Why:* triggers automatic restrictions.
*Fix:* verify immediately on creation.

## B. Warmup & cadence

**🔴 Skipping the aging/marination step.** *Symptom:* account created today, active today. *Why:* the
single most protective step; most shadowbans hit in the first two days. *Fix:* let it sit ~30 days
(2+ months for bought) before real activity.

**🔴 Posting before ever commenting.** *Symptom:* first action is a post. *Why:* classic new-bot pattern
and a top shadowban trigger. *Fix:* comment-first — lurk, then comments, then text posts, then links.

**Too much too fast.** *Symptom:* 5–10+ actions/day early, marathon sessions. *Why:* accounts doing
5–10/day collect removals; clean ones stay ≤3–4/day. *Fix:* one organic action per visit, spaced and
randomized.

**Fixed timing / no randomness.** *Symptom:* actions every N minutes on the dot, 24/7 activity. *Why:*
"instant bot detection." *Fix:* randomize intervals, session length, and active hours; give each account
human active-hours.

**Joining hundreds of subs at once.** *Symptom:* mass-subscribing on day one. *Why:* spam-pattern signal;
also pointless (home feed caps at ~250). *Fix:* join a handful at a time as the persona would.

**Constantly resetting cookies.** *Symptom:* wiping session data between logins. *Why:* erases accumulated
trust signals. *Fix:* preserve original session cookies.

## C. Karma

**🔴 Using free-karma subs (r/FreeKarma4U etc.).** *Symptom:* farming karma in dedicated karma subs.
*Why:* Reddit tags participants as spam-focused regardless of karma gained — a common shadowban trigger.
*Fix:* never touch them; earn karma by genuine commenting.

**Karma farming via reposts.** *Symptom:* reposting popular content to pile up karma. *Why:* officially
frowned upon; pattern-detectable. *Fix:* original comments/posts that add value.

**Chasing post karma over comment karma.** *Symptom:* only posting, never commenting. *Why:* comment karma
is the honest, safer signal; post-only accounts look inflated. *Fix:* comment karma is the base engine.

**Thinking karma alone unlocks everything.** *Symptom:* high karma but 2-week-old account expecting full
access. *Why:* age matters as much as karma; gates are age **and** karma. *Fix:* let the account age.

## D. Subreddit rules & posting

**🔴 Not reading the sub's rules before posting.** *Symptom:* posting blind. *Why:* mods enforce local
rules before karma can accrue; wrong format/topic/link gets removed instantly. *Fix:* read rules +
sidebar before the first post in any sub, every time.

**Not knowing the post was silently removed.** *Symptom:* "my post is up but gets no engagement." *Why:*
AutoMod removes silently (too new, too little karma, filtered link) — you think it's live, no one sees it.
*Fix:* verify from a logged-out view after posting; check hidden age/karma gates.

**Ignoring flair requirements.** *Symptom:* posting without a required flair. *Why:* AutoMod auto-removal.
*Fix:* select the required post flair.

**Reposting removed content unchanged.** *Symptom:* re-submitting the same thing after a removal. *Why:*
repeat-filter / mod-queue trap. *Fix:* revise to fit the rules, or ask the mods, before retrying.

**Dropping links in comments on a young account.** *Symptom:* URLs in early comments. *Why:* anti-spam
filters catch it on the way up. *Fix:* links go in a post's first comment on an aged/karma'd account, not
in comments early.

## E. Content quality

**🔴 Copy-paste / identical content across threads or accounts.** *Symptom:* same comment/title reused;
spintax with the same link. *Why:* spam/manipulation signal; "temporary bans for days/weeks quickly," and
same-link spintax flags the whole fleet. *Fix:* rewrite genuinely per thread; vary wording and vector.

**Generic AI sludge.** *Symptom:* comments that could fit any thread. *Why:* downvoted or removed as
low-value. *Fix:* answer the exact thread, add one specific detail (see content-playbook.md).

**Obvious AI writing.** *Symptom:* em-dashes, rule-of-three, "Great question!", buzzwords, bold subheads.
*Why:* Reddit users clock AI text fast, especially on promo accounts. *Fix:* run humanization.md before
posting.

**Low-effort comments.** *Symptom:* "this", "lol", "came here to say this." *Why:* reddiquette violation,
gets downvoted. *Fix:* upvote to agree; only comment when adding something.

## F. Promotion & etiquette

**🔴 Violating the 90/10 rule.** *Symptom:* most activity is self-links. *Why:* "if your only activity is
sharing your own links, it's spam regardless of quality." *Fix:* ≥90% genuine contribution across your
whole history; ≤10% promotion.

**🔴 Vote manipulation / accounts boosting each other.** *Symptom:* alts upvoting/commenting on your own
posts, buying votes, off-site "upvote this." *Why:* enforceable policy violation → suspension/permanent
ban; converts one flag into a fleet wipe. *Fix:* never cross-vote or cross-engage your own accounts.

**🔴 Ban evasion.** *Symptom:* new account continuing where a banned one left off. *Why:* separately
enforced; escalates. *Fix:* don't re-enter a sub/site you were banned from on a new account.

**DM-dominant behavior.** *Symptom:* account's main action becomes DMing. *Why:* throttled within days
(50/day → 2/day). *Fix:* DMs as a side effect; keep commenting 2–3×/day; ramp DM volume slowly.

**Begging for votes.** *Symptom:* "upvote if...", "help this reach front page." *Why:* reddiquette
violation. *Fix:* let content earn votes.

**Hard flip to promotion.** *Symptom:* clean account suddenly starts link-dropping. *Why:* the pattern
break is what filters catch. *Fix:* gradual, once, emerging from normal-looking activity.

## G. Diagnosing "what went wrong"

Map the user's complaint to likely causes:

| Complaint | Most likely causes (check in order) |
|---|---|
| "Posts disappear / no engagement" | Silent AutoMod removal (too new / low karma / filtered link) → shadowban → wrong flair |
| "Got banned fast" | Promoted too early → same content across accounts → one IP/fingerprint → free-karma subs |
| "Comments get downvoted" | Generic/AI sludge → didn't match sub culture → didn't read the thread |
| "Can't send DMs" | Karma/CQS too low → account too new → commercial VPN → looks like a sender not a user |
| "Whole batch banned at once" | Shared IP/fingerprint → identical content/spintax+same link → cohort concentration |
| "Was fine, then throttled" | Trust throttling after a ramp → DM-dominant → sudden volume jump |

When diagnosing, always ask for: account age, karma (post vs comment), IP/proxy setup, what the first
actions were, and whether content is unique. Those five answers explain most failures.
