# Homepage embellishment packet for Codex

> Goal: make `index.html` hammer three things the current page under-sells —
> **(1) how Claude AI is doing the work, everywhere; (2) how PilotBriefAI complements an EFB
> like ForeFlight or Garmin Pilot rather than competing with it; (3) the one-of-a-kind combination
> of AI weather synthesis + live ATC audio + live ADS-B tracking in one app.**
> All copy below is drop-in. Keep the existing dark theme, Ionicons, flight-category chips, and
> `var(--accent)` styling. Every factual claim here is true to the shipping app.

---

## A. NEW SECTION — "Complements your EFB" (highest priority)

Place this **right after the hero / trial band**, before or just after the `#decision` section.
This is the most important missing piece. Frame it as cooperation, not competition.

**Eyebrow:** Works with what you already fly
**Headline:** The pre-flight decision layer your EFB is missing.
**Lead:** ForeFlight and Garmin Pilot are brilliant at charts, plates, filing, and navigation. None
of them tell you — in plain English, judged against *your* minimums — whether today is a go. That's
the gap PilotBriefAI fills. Brief here. Decide here. Then file and fly in the EFB you already trust.

**Three-column "PilotBriefAI vs your EFB vs raw weather sites" or a simple workflow strip:**

Workflow strip (cleaner than a combative table):
- **1 — Brief in PilotBriefAI.** Claude synthesizes live weather into a go/no-go judged against your
  personal minimums and aircraft. *(icon: `sparkles` or `partly-sunny`)*
- **2 — Cross-check the raw data.** Live METAR/TAF, crosswind, density altitude, route hazards,
  winds aloft — all decoded for you. *(icon: `analytics`)*
- **3 — File & fly in your EFB.** Take the decision to ForeFlight or Garmin Pilot for charts, plates,
  filing, and georeferenced navigation. *(icon: `navigate`)*

**Pull-quote / callout to include:**
> "Your EFB shows you the weather. PilotBriefAI tells you what it means for *you* — then gets out of
> the way so you can fly."

**Optional comparison table** (only if Codex wants one — keep it factual, not trashy):

| | Raw weather sites (aviationweather.gov / 1800wxbrief) | EFBs (ForeFlight / Garmin Pilot) | **PilotBriefAI** |
|---|---|---|---|
| Live METAR/TAF/NOTAM data | ✅ | ✅ | ✅ |
| Charts, plates, filing, georef navigation | ❌ | ✅ | ❌ (by design — use your EFB) |
| **AI go/no-go judged against *your* minimums** | ❌ | ❌ | ✅ |
| **Plain-English PAVE risk synthesis** | ❌ | ❌ | ✅ |
| **Live ATC audio in the briefing flow** | ❌ | ❌ | ✅ |
| **Live ADS-B tracking on VFR sectionals** | ❌ | partial | ✅ |
| Price | Free | $100–$300+/yr | from $39.99/yr |

> Note the honest ❌ on charts/filing/navigation — that's the point. We're the decision layer, not a
> replacement EFB. This honesty *builds* trust with the EFB-owning pilot.

---

## B. NEW SECTION — "The one-of-a-kind combination" (the moat thesis)

Place after the features grid. This states the differentiator the current page never says out loud.

**Eyebrow:** Three tools. One app. No one else has all three.
**Headline:** AI briefings, live ATC, and live ADS-B — together.
**Lead:** Plenty of apps do one of these. PilotBriefAI is the only one that puts an AI weather
briefer, real-time tower/ground/CTAF audio, and live aircraft tracking on a VFR sectional in a single
cockpit-grade app — so the whole picture of your departure comes together in one place.

**Three cards:**

1. **AI-synthesized briefings** *(icon: `sparkles`)*
   Claude reads live FAA/NOAA data and turns it into a plain-English go/no-go judged against your
   minimums — not a wall of decoded strings.

2. **Live ATC audio** *(icon: `radio`)*
   Stream live tower, ground, and CTAF from LiveATC.net right in the briefing flow. Hear how busy the
   field is and what the weather's actually doing before you key the mic.

3. **Live ADS-B tracking** *(icon: `airplane`)*
   Watch real traffic — including your own tail — move across a public-domain VFR sectional in real
   time, with position updates every ~15 seconds and dead-reckoning between hits.

**Closing line under the cards:**
> Weather synthesis, the sound of the field, and the traffic picture — the situational awareness an
> EFB doesn't give you, in the minutes before you fly.

---

## C. EXPAND the existing `#ai` section — make Claude's "how" concrete

The current 3-step flow (Live data → Your numbers → PAVE verdict) is good. Keep it, but add a second
row of "what Claude actually does" so technical pilots believe it. Add these as a 4-up grid or a
"under the hood" strip beneath the existing steps:

**Eyebrow add-on:** Built to be trusted by pilots who read the raw data

- **Reasons against your exact numbers.** Claude doesn't apply generic thresholds — it weighs ceiling,
  vis, wind, crosswind, icing, and density altitude against the personal minimums and the specific
  aircraft in your profile.
- **Hazards scoped to your corridor.** SIGMETs, AIRMETs, TFRs, and PIREPs are checked against your
  actual route polygon — not a 500-mile region you have to mentally filter.
- **NOTAMs read like a human would.** NOTAMs are paginated from the FAA and classified by ICAO Q-code
  for completeness and accuracy before Claude ever summarizes them — so nothing critical silently
  drops.
- **A verdict engineered not to fail.** The safety-critical go/no-go is produced by a reliability-
  hardened, salvage-and-retry pipeline — the verdict can't fail silently on you.
- **Fast enough to actually use.** A full multi-source briefing returns in roughly 15 seconds thanks
  to a parallelized fetch engine.

**Add a small "Powered by Claude" trust line** near the verdict mockup:
> Briefings are generated with Anthropic's Claude. Your briefing inputs are sent to Anthropic's API to
> produce the summary — see our Privacy Policy.

---

## D. Sprinkle Claude "fingerprints" across the existing feature cards

Right now the VFR/IFR/CFI cards list features but never credit Claude with the intelligence. Add a
small **"Claude" pill/badge** (use `var(--accent)` `#38bdf8` text on a faint surface) on every card
or bullet where the AI is doing the reasoning, and tweak the wording so the *intelligence* is visible:

In the **IFR planning suite** card:
- "AI Alternate Advisor ranked by flyability" → **"Claude ranks your alternates by real flyability —
  not just legal minimums — and tells you *why* each one is or isn't a good out."**
- "Winds aloft and cruise altitude recommendations" → **"Claude reads FD winds at multiple levels and
  recommends your best cruise altitude for tailwinds, terrain, and forecast — with the reasoning."**

In the **VFR safety suite** card:
- "Route hazards, fuel, FBOs, ATC audio, and Windy maps" → split ATC audio out as its own line
  (it's a differentiator, see §B) and add **"Claude calls out icing, turbulence, and IFR conditions on
  your corridor by name."**

In the **CFI toolkit** card:
- "FAR/AIM-cited teaching callouts" → **"Claude flags teachable moments in every briefing with FAR/AIM
  citations and classic decision traps — your student's briefing becomes a lesson plan."**

**Suggested reusable badge markup** (Codex can style):
```html
<span class="ai-badge"><ion-icon name="sparkles"></ion-icon>Claude</span>
```
```css
.ai-badge{display:inline-flex;align-items:center;gap:4px;font-size:.72rem;font-weight:600;
  color:var(--accent);background:rgba(56,189,248,.12);border:1px solid rgba(56,189,248,.3);
  padding:2px 8px;border-radius:999px;}
.ai-badge ion-icon{font-size:.85rem;}
```

---

## E. NEW "by the numbers" credibility strip (concrete data the page lacks)

A thin band of stat tiles adds the proof the current page is missing. All true to the app:

- **~15s** — from tap to a full multi-source AI briefing
- **8+** — live data feeds synthesized per briefing (METAR, TAF, NOTAM, SIGMET, AIRMET, TFR, PIREP, winds aloft)
- **4** — FAA flight categories color-coded everywhere (VFR / MVFR / IFR / LIFR)
- **100%** — U.S. government public-domain weather & NOTAM sources
- **14 days** — full IFR-tier trial, no credit card

*(Keep the tone factual — these are descriptive, not performance guarantees.)*

---

## F. Update the "Why PilotBriefAI is different" section

The third card currently buries the moat. Replace the three cards with these four so EFB-complement
and the one-of-a-kind combo are explicit:

1. **Your minimums matter.** Every briefing is judged against your certificate level, weather limits,
   and the exact aircraft you're flying — not generic averages.
2. **It complements your EFB.** Decide here, then file and fly in ForeFlight or Garmin Pilot. We're
   the go/no-go layer, not a chart replacement.
3. **Three tools in one cockpit.** AI weather synthesis, live ATC audio, and live ADS-B on sectionals
   — a combination no other app offers.
4. **Honest about its role.** A situational-awareness aid that makes you a sharper decision-maker. The
   go/no-go is always yours.

---

## G. FAQ additions (add a short FAQ section near the footer)

These directly serve the positioning and pre-empt the #1 objection:

- **Do I still need ForeFlight or Garmin Pilot?**
  Yes — and keep them. PilotBriefAI doesn't do charts, plates, filing, or in-flight navigation. It's
  the pre-flight decision layer: synthesize the weather, check it against your minimums, get a clear
  go/no-go, then take that decision into your EFB to file and fly.
- **What makes it different from a weather app?**
  Weather apps and EFBs show you conditions. PilotBriefAI uses Claude to *interpret* those conditions
  against your personal minimums and aircraft, then adds live ATC audio and live ADS-B tracking — the
  full situational picture, not just raw data.
- **Which AI does it use?**
  Anthropic's Claude. It reads live FAA/NOAA data server-side and produces the plain-English PAVE
  analysis and Go / Marginal / No-Go result.
- **Is this an official weather briefing?**
  No. It's a situational-awareness aid — always get an official briefing from an FAA-approved source
  such as 1800wxbrief.com. The go/no-go decision is always yours as PIC.
- **How does the free trial work?**
  14 days of full IFR-tier access, no credit card, one per pilot.

---

## H. Quick hero tweak (optional but high-leverage)

The hero subhead is strong. Consider adding one more line under the lead that plants the moat + EFB
positioning immediately:

> **Sub-lead add:** "AI weather synthesis, live ATC audio, and live ADS-B tracking in one app — the
> pre-flight decision layer that works alongside ForeFlight and Garmin Pilot."

And swap the second hero deck-card or add a third micro-card referencing **live ATC** and **ADS-B** so
the differentiators appear above the fold (e.g. a small "🔊 KAUS Tower — LIVE" chip and a "1 tail in
range" ADS-B chip).

---

## I. NEW SECTION — Full feature comparison chart (mirror the in-app table)

Add a full plan-comparison table, placed **directly under the pricing cards** in `#pricing` (the
cards give the headline; this table closes the sale). The data below is the **exact in-app feature
matrix** from `constants/tiers.ts` — same rows, same values, same order. Don't paraphrase the values;
pilots cross-shop on these.

The table uses the tier-color CSS variables already in `styles.css` (`--free`, `--vfr-plan`,
`--ifr-plan`, `--cfi-plan`, `--accent`, `--go`/`--vfr` green, `--border`, `--surface`, `--muted`).
On mobile, make the table horizontally scrollable (`overflow-x:auto`) with the first column sticky.

### Drop-in markup

```html
<section class="section alt" id="compare">
  <div class="container">
    <div class="section-head center">
      <p class="eyebrow">Every feature, every plan</p>
      <h2>Compare plans in full.</h2>
      <p class="lead">The same feature matrix you'll see in the app. Core decision tools are free on
      every plan — paid tiers add route planning, the IFR suite, and the CFI toolkit.</p>
    </div>

    <div class="compare-wrap">
      <table class="compare">
        <thead>
          <tr>
            <th class="feat">Feature</th>
            <th style="--tier:var(--free);">Free</th>
            <th style="--tier:var(--vfr-plan);">VFR</th>
            <th class="hot" style="--tier:var(--ifr-plan);">IFR</th>
            <th style="--tier:var(--cfi-plan);">CFI</th>
          </tr>
          <tr class="price-row">
            <td class="feat"></td>
            <td>Free</td><td>$39.99/yr</td><td>$59.99/yr</td><td>$119.99/yr</td>
          </tr>
        </thead>
        <tbody>
          <tr class="group"><td colspan="5">Core — free on every plan</td></tr>
          <tr><td class="feat">AI preflight briefings / month</td><td>3</td><td>30</td><td>Unlimited&dagger;</td><td>Unlimited&dagger;</td></tr>
          <tr><td class="feat">Live METAR and Go/No-Go</td><td class="y"></td><td class="y"></td><td class="y"></td><td class="y"></td></tr>
          <tr><td class="feat">Personal minimums profile</td><td class="y"></td><td class="y"></td><td class="y"></td><td class="y"></td></tr>
          <tr><td class="feat">Animated weather maps (Windy)</td><td class="y"></td><td class="y"></td><td class="y"></td><td class="y"></td></tr>

          <tr class="group"><td colspan="5">VFR safety &amp; planning suite</td></tr>
          <tr><td class="feat">AI multi-airport route briefing</td><td class="n"></td><td class="y"></td><td class="y"></td><td class="y"></td></tr>
          <tr><td class="feat">Crosswind component analysis</td><td class="n"></td><td class="y"></td><td class="y"></td><td class="y"></td></tr>
          <tr><td class="feat">Density altitude &amp; performance</td><td class="n"></td><td class="y"></td><td class="y"></td><td class="y"></td></tr>
          <tr><td class="feat">IMSAFE personal check</td><td class="n"></td><td class="y"></td><td class="y"></td><td class="y"></td></tr>
          <tr><td class="feat">AI route hazard analysis</td><td class="n"></td><td class="y"></td><td class="y"></td><td class="y"></td></tr>
          <tr><td class="feat">Fuel &amp; FBO availability on route</td><td class="n"></td><td class="y"></td><td class="y"></td><td class="y"></td></tr>
          <tr><td class="feat">Live ATC audio</td><td class="n"></td><td class="y"></td><td class="y"></td><td class="y"></td></tr>

          <tr class="group"><td colspan="5">IFR planning suite</td></tr>
          <tr><td class="feat">AI Alternate Advisor</td><td class="n"></td><td class="n"></td><td class="y"></td><td class="y"></td></tr>
          <tr><td class="feat">AI winds aloft + altitude advisor</td><td class="n"></td><td class="n"></td><td class="y"></td><td class="y"></td></tr>
          <tr><td class="feat">Hourly NBM point forecast</td><td class="n"></td><td class="n"></td><td class="y"></td><td class="y"></td></tr>
          <tr><td class="feat">AI terrain awareness</td><td class="n"></td><td class="n"></td><td class="y"></td><td class="y"></td></tr>

          <tr class="group"><td colspan="5">Limits</td></tr>
          <tr><td class="feat">Saved routes</td><td>0</td><td>10</td><td>Unlimited</td><td>Unlimited</td></tr>
          <tr><td class="feat">Favorite airports</td><td>3</td><td>10</td><td>Unlimited</td><td>Unlimited</td></tr>
          <tr><td class="feat">Aircraft profiles</td><td>1</td><td>3</td><td>Unlimited</td><td>Unlimited</td></tr>

          <tr class="group"><td colspan="5">CFI instructor toolkit</td></tr>
          <tr><td class="feat">AI teaching callouts (FAR/AIM-cited)</td><td class="n"></td><td class="n"></td><td class="n"></td><td class="y"></td></tr>
          <tr><td class="feat">Student profiles</td><td class="n"></td><td class="n"></td><td class="n"></td><td>Up to 5</td></tr>
          <tr><td class="feat">Briefing PDF export &amp; share</td><td class="n"></td><td class="n"></td><td class="n"></td><td class="y"></td></tr>
          <tr><td class="feat">Early access to new features</td><td class="n"></td><td class="n"></td><td class="n"></td><td class="y"></td></tr>
          <tr><td class="feat">Priority support</td><td class="n"></td><td class="n"></td><td class="n"></td><td class="y"></td></tr>
        </tbody>
      </table>
    </div>
    <p class="compare-foot">&dagger; Unlimited under fair-use limits. All AI features are powered by Anthropic's Claude.</p>
  </div>
</section>
```

### Drop-in CSS

```css
.compare-wrap{overflow-x:auto;border:1px solid var(--border);border-radius:16px;background:var(--surface);}
.compare{width:100%;border-collapse:collapse;min-width:640px;font-size:.93rem;}
.compare th,.compare td{padding:12px 14px;text-align:center;border-bottom:1px solid var(--border);white-space:nowrap;}
.compare thead th{font-weight:700;color:var(--tier,var(--accent));font-size:1rem;}
.compare .price-row td{color:var(--muted);font-size:.8rem;font-weight:600;padding-top:0;border-bottom:1px solid var(--border);}
.compare th.feat,.compare td.feat{text-align:left;color:var(--secondary);position:sticky;left:0;background:var(--surface);white-space:normal;min-width:220px;font-weight:500;}
.compare thead th.feat{background:var(--surface);}
.compare th.hot{position:relative;}
.compare th.hot::after{content:"Best fit";position:absolute;top:-9px;left:50%;transform:translateX(-50%);
  font-size:.6rem;font-weight:700;letter-spacing:.04em;color:#0b1220;background:var(--ifr-plan);
  padding:2px 8px;border-radius:999px;}
.compare tr.group td{text-align:left;background:var(--surface-alt);color:var(--accent);
  font-size:.75rem;font-weight:700;letter-spacing:.06em;text-transform:uppercase;padding:10px 14px;}
.compare td.y::before{content:"\2713";color:var(--vfr-plan);font-weight:800;font-size:1.05rem;} /* check */
.compare td.n::before{content:"\2013";color:var(--muted);} /* en-dash */
.compare tbody tr:hover td:not(.group){background:rgba(56,189,248,.05);}
.compare tbody tr:hover td.feat{background:color-mix(in srgb,var(--surface) 92%,var(--accent));}
.compare-foot{color:var(--muted);font-size:.8rem;margin-top:12px;text-align:center;}
```

> Codex: if your existing tier variable for VFR green differs (`--vfr` flight-category vs `--vfr-plan`
> tier color), use `--vfr-plan` for the tier column and the green check. Keep the IFR column flagged
> "Best fit" to match the featured pricing card.

---

## Priority order for Codex
1. **§A** — Complements your EFB (the biggest gap)
2. **§B** — One-of-a-kind combination (AI + LiveATC + ADS-B)
3. **§D + §C** — Claude fingerprints everywhere + concrete "how"
4. **§I** — Full feature comparison chart under pricing
5. **§E, §F, §G, §H** — proof strip, sharpened differentiators, FAQ, hero tweak
