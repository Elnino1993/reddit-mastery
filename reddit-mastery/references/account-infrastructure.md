# Account Infrastructure — accounts, IPs, browsers, fingerprints, shadowbans

The operational layer under everything. Content quality doesn't matter if the account gets nuked for how
it connects. **Core principle heard across every source: bans come from behavior, not devices — but bad
infrastructure removes your margin for error and makes one mistake take down the whole fleet.**

Sourced from BlackHatWorld NSFW/OFM warmup threads, Multilogin's warmup guide, and this project's own
bot KB. Numbers are what practitioners report, not guarantees; treat them as starting calibration.

---

## Accounts: buy, age, or grow

- **Fresh + aged in-house is the default.** Create the account, then let it "marinate" before real
  activity. Reported minimums: **30 days** in-house (14 days works but is "more risky"); **2+ months**
  for anything you plan to promote hard from.
- **Buying accounts:** ~**$6–8** for an established one; bulk buyers grab blank US accounts and farm them
  behind proxies. Sellers named in threads: signals.sh, rakumm.com. (Vet independently — seller quality
  varies and this is against Reddit's ToS.)
- **When buying, comment karma > post karma.** High post karma + near-zero comment karma = artificially
  upvoted = manipulation red flag. Avoid it.
- **Email tells:** prefer accounts on a disposable/unknown email you can't recover — that inability
  actually proves the account wasn't repeatedly restored after past bans. Accounts with a pre-assigned
  recoverable email + massive karma are often ban-recycled; avoid.
- **Age is not immunity.** A 10-year, high-karma account can still be banned. Old accounts get no free
  pass; behavior is what matters.
- **Physical-device path (highest trust, doesn't scale):** secondhand iPhone 8/X (~$60–70) or cheap
  Android, factory reset, fresh iCloud/Google, a $5/mo SIM. One phone ≈ one account. Use this for a
  flagship account, proxies for a fleet.
- **Detachment principle:** "Sooner or later they will be banned." Don't get attached; plan to burn and
  replace. Build a pipeline, not a prized possession.

## IPs & proxies

- **One account = one IP. Never share.** Logging many accounts from one IP or fingerprint is the classic
  cause of **simultaneous fleet bans**.
- **Residential or mobile (4G) from real ISPs.** Cheap datacenter proxies get flagged immediately.
  Ideal: a mobile IP in the same region as registration.
- **Commercial VPNs are a red flag.** Fresh accounts on NordVPN often can't send more than 1–3 DMs and
  sometimes get banned outright. ProtonVPN is a lighter alternative but still worse than residential.
- **Consistency beats location.** Which country the IP is in matters less than not hopping around. Keep
  the same ASN; wait **2–3 days before changing geographic location**; don't random-IP-hop between
  sessions. This project's rule: **rotate the mobile IP once before each account, then keep it stable for
  that account's session.**
- **Match proxy region to target subs** where you can (US proxy for US subs), but a stable non-US IP can
  still work if you engage organically.

## Antidetect browser & fingerprint

- **The fleet standard:** a dedicated antidetect browser giving each account its own profile with a unique,
  coherent fingerprint (canvas, WebGL, fonts, UA, screen, timezone) and isolated cookies/cache/localStorage.
  Named tools: Dolphin Anty, AdsPower. This project uses an antidetect browser driven over CDP, one profile
  per account, plus Camoufox (Firefox engine) where it needs to pass stricter fingerprint checks.
- **Dissent worth knowing:** some practitioners claim Reddit still detects antidetect browsers and prefer
  physical phones. Reality: a *coherent* fingerprint on a good residential IP with human behavior is what
  passes; an *incoherent* one (Chrome fingerprint on a Firefox engine, impossible core counts, geo not
  matching IP) is what gets caught.
- **Fingerprint coherence rules (from this project's fixes):**
  - Keep the fingerprint **stable from account creation.** Don't regenerate it casually.
  - Make derived values realistic — no impossible `hardwareConcurrency` (512 cores), UA must match the
    engine, WebGL vendor must match the claimed OS, timezone/geo must match the IP.
  - If you must change the browser engine, **regenerate a fresh coherent fingerprint for the new engine**
    rather than bolting the old one on — and do it while the profile is stopped, not live.
- **Cookie hygiene:** preserve original session cookies; **don't reset cookies constantly** (it erases
  trust signals). Pre-warmed cookies reportedly cut early CAPTCHA frequency 50–70%.
- **Bought accounts:** import into a fresh profile with a unique fingerprint. **Don't change password/email
  immediately** — space those changes out to Days 3–5. Sudden credential changes trigger suspicion flags.

## Human-behavior layer (the part that actually prevents bans)

Because bans come from behavior, the automation must not behave like automation:

- **Randomized everything:** delays between actions, session lengths, active hours, mouse paths, typing
  speed with occasional typos, read pauses scaled to text length. Never fixed intervals.
- **Respect active hours** per account (a persona that only posts 2pm–11pm looks human; a 24/7 account
  does not).
- **Cap actions per session/day** (this project caps ~5 actions per visit; clean operators stay ≤3.5
  actions/day, accounts that got removals were doing 5–10/day).
- **Anti-concentration:** don't let multiple fleet accounts pile into the same subreddit through similar
  IPs at the same time — that correlation is itself a detection vector.
- **DMs must look incidental.** The accounts that sustain promo "didn't behave like senders at all — they
  looked like normal users first, and DMs were a side effect." Accounts that flip to DM-dominant get
  throttled within days (one went 50 DMs/day for 3 days → capped at 2/day).

## Shadowban & suspension: detect, then abandon

- **Detect anonymously only.** Check the account **logged out / in a private window** (or via old.reddit
  HTML). If the profile or a just-posted comment is invisible to a logged-out viewer with no mod
  message, treat it as a shadowban. A true shadowban looks normal from *your* side and invisible from
  outside — never diagnose it while logged in.
- **Routine check cadence:** run an anonymous health check **before** a full fleet run and after risky
  actions. After a ban wave, expect a large share of the fleet to be shadowbanned (this project saw
  ~half), and separate live from dead before wasting sessions on dead accounts.
- **Recovery is mostly abandonment.** Consensus: no reliable un-shadowban. The Multilogin playbook: stop
  logging in immediately → switch to a clean residential proxy from a *different* provider → spin up fresh
  profiles with new fingerprints → wait 24–48h → start fresh. Don't create a new account to continue
  posting where the old one was banned (that's ban evasion, which is separately enforced).
- **Don't over-write dead accounts.** Some "bans" after a wave are recoverable shadowbans from
  idleness + cohort correlation, not hard bans — this project recovered ~5 of 23 falsely written off.
  Verify before deleting.

## Environmental headwinds to price in

- **CQS (Contributor Quality Score)** is Reddit's current lever gating DM volume and reach. Higher
  genuine participation raises it; spammy behavior lowers it. Accounts at ~1,000–1,500 karma with good
  CQS can send ~30 DMs/hour; fresh/low-CQS accounts get 1–3 and stop.
- **Trust throttling / suspicion decay:** Reddit lets an account ramp, then deliberately slows it to
  observe. Trust doesn't "reset" on good behavior so much as **suspicion decays over time** — which is why
  extra weeks of non-commercial activity buy real protection.
- **Spam-filter escalations** (a notable one in early 2025) periodically make everything harder
  regardless of tactics. When ban rates spike fleet-wide, slow down rather than push harder.
