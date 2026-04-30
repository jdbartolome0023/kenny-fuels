# Kenny Fuels - Weekly Tasks
# Week: Apr 23 - Apr 30, 2026 (Thu-Thu)
# Session dates: Apr 27, Apr 28, Apr 29, Apr 30

Note: Apr 23 changes are logged in week-apr-16-23.md. This file covers Apr 27-30.

---

## Optimisations Made

### P1 - Critical

#### Conversion Tracking Fix (Apr 30)
- Client granted Google Ads Admin access. Full conversion action audit completed.
- Root cause: 4 PURCHASE conversion actions were all set as Primary — every real purchase was being counted 4 times, inflating conversion metrics 3-4x and distorting Smart Bidding signals.
- Fix: Set 3 duplicate purchase actions to Secondary via API.

| Conversion Action | Before | After |
|---|---|---|
| Kenny Fuels - GA4 (web) purchase | Primary | Primary (kept) |
| Google Ads Purchase | Primary | Secondary |
| Purchase GTM (1) | Primary | Secondary |
| Purchase_2_GTM_GA4 | Primary | Secondary |

- Contact Us Form: set to Secondary (tag broken, 0 conversions, was Primary — influencing Smart Bidding with no data)
- Book appointment GTM: set to Secondary (tag broken, 0 conversions, was Primary)
- ATC_2_GTM_GA4: dead duplicate, removed manually by client (could not be removed via API — GA4-imported action)
- Misconfigured warnings on Add to Basket, Begin Checkout, Book appointment: left intentionally — setting Primary would make Smart Bidding optimise toward cart adds, not purchases

Final Primary conversion actions: Kenny Fuels - GA4 (web) purchase, Clicks to call, Calls from ads, Local actions (Google-hosted)

Scripts: fix_conversion_tracking_apr30_2026.py, fix_contact_us_form_apr30_2026.py, fix_book_appointment_apr30_2026.py

---

#### Home Heating Oil Search — Full Rebuild (Apr 30)
Previous state: campaign had only "near me" phrase match keywords getting 5-6 impressions/day, and bidding strategy was confirmed still on Maximize Clicks (TARGET_SPEND) despite Apr 28 notes saying it was changed.

- Fixed bidding strategy: changed from Maximize Clicks (TARGET_SPEND) to Maximize Conversion Value (no target ROAS)
- Added 29 geographic phrase match keywords covering full service area (Wexford, Wicklow, Carlow, town-level, Ireland-wide)
- Added 7 brand phrase match keywords (kenny fuels variants)

Geographic keywords added:
- Wexford: heating oil wexford, home heating oil wexford, kerosene prices wexford, heating oil prices wexford, oil prices wexford, kerosene wexford, home heating oil delivery wexford
- Wicklow: heating oil wicklow, home heating oil wicklow, kerosene prices wicklow, heating oil prices wicklow, oil prices wicklow, kerosene wicklow
- Carlow: heating oil carlow, home heating oil carlow, kerosene carlow, oil prices carlow
- Town-level: heating oil gorey, heating oil enniscorthy, heating oil arklow, heating oil ferns, kerosene gorey, kerosene enniscorthy, kerosene arklow
- Ireland-wide: home heating oil ireland, kerosene prices ireland, heating oil prices ireland, buy heating oil ireland, order heating oil ireland

Brand keywords added: kenny fuels (broad), kenny fuels ferns, kennys fuels, kenny fuel, kenny fuels wexford, kenny fuels wicklow, kenny fuels gorey

Result: impressions jumped from 5-6/day to 70 on Apr 30 (day 1 of new keywords live).

---

### P2 - High

#### Brand & General Search — Budget Reduction (Apr 30)
- Reduced from €110/day to €80/day
- Reason: campaign spiked to €179.40 on Apr 29 (163% of daily budget) after Apr 28 bidding strategy change freed up Maximize Conversion Value to spend aggressively
- Total account budget now €165/day (was €195/day)
- Monitor over next few days — increase back to €110 once spend stabilises

#### Brand & General Search — Competitor Negatives Added (Apr 28)
- Added `flogas` as campaign-level negative (broad) — Flogas is a competitor brand
- Added to both Brand & General Search and Gas Bottle & Cylinders: `burkes oil`, `burkes`, `topoil`, `top oil`, `naasoil`, `naas oil`, `certa`, `certas`
- Added `oil tank` to Brand & General Search (Kenny Fuels doesn't sell tanks)
- These were generating wasted spend: "oil heating" keyword was triggering at €8.13 CPC with 0 conversions

#### Brand & General Search — Negative Keyword Audit (Apr 29)
- Reviewed all 200+ negative keywords — list was a generic agency template dump
- Removed `review` and `reviews` (broad) — were blocking "kenny fuels reviews" brand reputation searches
- Applied Google's suggested fix for conflicting negative keywords (auto-removed conflicting terms)

#### Gas Bottle & Cylinders — Keyword Additions (Apr 27 + Apr 29)
Apr 27: Changed 12 keywords from broad to phrase match (Superser, butane, calor, propane, gas cylinder, forklift cylinder variants)

Apr 29: Added 10 high-volume missing keywords to Gas Cylinders ad group (all phrase match):
- "butane gas cylinders" — 390/mo, €0.76
- "gas cylinder near me" — 320/mo, €0.34
- "gas bottle near me" — 260/mo, €1.30
- "lpg gas near me" — 260/mo, €1.79
- "propane gas near me" — 90/mo, €0.35
- "gas refill near me" — 90/mo, €2.23
- "gas cylinders ireland" — 50/mo, €1.38
- "butane gas near me" — 40/mo, €0.50
- "flo gas ireland" — 30/mo, €0.74
- "gas canister ireland" — 30/mo, €0.08

Also added: "gas canister refills near me" — 210/mo (rescued from paused Brand & General ad group)

#### Home Heating Oil Search — Near-Me Keywords Added (Apr 29)
Added 4 missing near-me keywords plus emergency term:
- "heating oil near me" — 170/mo, €0.72
- "home heating oil near me" — 140/mo, €0.50
- "cheap heating oil near me" — 90/mo, €1.27
- "heating oil supplier near me" — 50/mo, €1.06
- "emergency heating oil delivery near me" — 320/mo, €11.21

#### Brand & General Search — Keyword Pauses (Apr 30)
- Paused `home oil` (phrase) — QS 0, €71.30 spend in 30 days, 0 conversions, was generating irrelevant "oil heating" searches
- Paused `order oil` (phrase) — too generic, QS 0, 0 conversions
- Added `oil heating` [exact] as campaign-level negative — €16.26 spent in last 7 days, 0 conversions

#### Gas Bottle & Cylinders — Negative Added (Apr 30)
- Added `coal merchants` [phrase] as campaign-level negative — wrong product category, 0 conversions

---

### Ad Copy — 10 Ad Groups Rewritten (Apr 28 - Apr 30)

**Pattern found:** Every ad group had a "skeleton" second ad with only 3 headlines all pinned to H1/H2/H3 — causing POOR ad strength account-wide.

**Apr 28 rewrites (Brand & General Search):**
- Heating Oil Prices Near Me Today: paused skeleton ad, rewrote with 15 headlines, H1 pin only, 4 descriptions
- Heating Oil Suppliers Near Me: paused skeleton ad, rewrote with 15 headlines, H1 pin only, 4 descriptions
- Wexford Heating Oil Suppliers: rewrote with 15 headlines, 4 descriptions
- Home Heating Oil Carlow: rewrote with 15 headlines, H1 pin only
- Heating Oil Delivery Wicklow: paused skeleton ad, rewrote with 15 headlines, H1 pin only
- Heating Oil For Homes Wicklow: rewrote with 15 headlines, H1 pin only

**Apr 29 rewrites (Brand & General Search):**
- Gas Cylinder For Sale: paused skeleton ad, rewrote with gas-specific headlines (removed heating oil/coal/firewood descriptions)
- Heating Oil For Homes Wicklow: fixed 2 truncated descriptions (first letter cut off by Google)
- Top Heating Oil Supplier Wicklow: paused skeleton ad, rewrote with 11 new Wicklow-specific headlines

**Apr 30 rewrites (Brand & General Search + Home Heating Oil Search):**
- Kenny Fuels brand ad group: paused weaker ad (45 conv vs 53), rewrote winner with clean brand headlines, removed "OIl" typo
- Fuel Oil For Home Heating: paused skeleton ad, replaced all 8 gas bottle headlines with heating oil content
- Heating Oil Prices Today Near Me: paused skeleton ad, rewrote with 15 headlines
- Wexford Home Heating Oil Services: rewrote with H1 pin only
- Bags Of Firewood For Sale: paused skeleton ad, rewrote with 15 firewood headlines
- Buy Home Heating Oil Carlow: paused skeleton ad, rebuilt from scratch with Carlow-specific content
- Kerosene Heating Oil Near Me: paused skeleton ad, rewrote with 15 kerosene-specific headlines

---

### Dead Ad Group Cleanup — 69 Ad Groups Paused (Apr 27 - Apr 29)

**Apr 27 — 8 ad groups paused** (Brand & General Search, 0 impressions/conversions):
Specific names to confirm from Google Ads Change History (Tools > Change History, filter Apr 27).

**Apr 28 — 46 ad groups paused** (Brand & General Search):
All had 0 impressions and 0 conversions over last 30 days. Categories: firewood, kiln dried logs, hardware, coal, lubricants, and other irrelevant categories. Heating oil, gas bottle/cylinder, propane/butane/LPG and kerosene ad groups were excluded from the pause.

**Apr 29 — 15 ad groups paused** (Brand & General Search, 0 impressions over last 30 days):
Buy Firewood, Butane Gas Near Me, Buy Hardwood Firewood, Local Firewood For Sale, Log Drying Kiln For Sale, Best Gas Supplier Wexford, Gas Bottle Refill Wicklow, Gas Tank Suppliers Near Me, Best Places To Buy Firewood, Bottled Gas Delivery Carlow, Gas Canister Refills Near Me, Buy Home Heating Oil Near Me, Kiln Firewood For Sale Near Me, Heating Oil Distributors Near Me, Emergency Heating Oil Delivery Near Me

Note: Before pausing, DataForSEO volumes were checked on all keywords. Salvageable keywords were moved to appropriate campaigns (gas canister refills near me to Gas Bottle & Cylinders; emergency heating oil delivery near me to Home Heating Oil Search).

**Apr 29 — 8 ad groups paused** (Brand & General Search, gas/butane terms duplicated by Gas Bottle & Cylinders campaign):
Butane Gas Cylinders, Gas Cylinders Near Me, Buy Heating Oil Near Me, Buy Propane Gas Wicklow, Butane Suppliers Near Me, Butane Gas Refill Near Me, Butane Gas Canisters Near Me, Butane Gas Suppliers Near Me

---

### Account Assets — Callouts & Structured Snippet (Apr 29)

Added 6 account-level callouts (apply across all campaigns):
1. EU Award Winner 2021
2. Free Quote Online
3. Trackable Delivery
4. Emergency Deliveries
5. No Minimum Order
6. Serving Wexford & Wicklow

Updated Brand & General Search structured snippet (Service catalog):
- Old: Heating oil, Gas, Solid fuel, Kiln-dried firewood, Engine lubricants, Hardware, Tanks
- New: Home Heating Oil, Gas Cylinders, Solid Fuel, Kiln-Dried Firewood, Engine Lubricants, Composite Decking, Composite Fencing, Oil Tanks, Safety & Workwear

---

### Tracking & GTM Audit (Apr 29)

Audited kennyfuels.ie source. Found 2 GTM containers, 2 GA4 properties, 1 Meta Pixel.

GTM containers:
- GTM-WD9M7345: Empty, under Outposter account (our access, never configured)
- GTM-5Z97JLX: Active on site, managed by Graphedia (no access)
- GTM-TQR899VB: Active on site, managed by Graphedia (no access)

Action required: Ask Graphedia to grant josette@outposter.com.au access to GTM-5Z97JLX and GTM-TQR899VB. Needed to fix Contact Us Form and Book appointment GTM broken tags.

---

## Pending Client Actions

1. **Budget approval** (~€1,400/week total) — CRITICAL, blocks hardware campaign launch
2. **GTM access from Graphedia** — needed to fix Contact Us Form and Book appointment GTM broken tags (both currently Secondary so no bidding impact, but tags are broken)

---

## Hardware Campaigns — Status

ON HOLD pending budget approval. Budget email sent to client Apr 28.

Plan once approved:
- Launch KF - Hardware | Composite Decking first (€15/day, Maximise Clicks)
- Apply: Hardware Campaigns - Fuel Exclusions negative list
- Then: Composite Fencing, Acoustic Panels, Safety & Workwear one by one

---

## Monitor

- Brand & General Search budget: confirm spend holds under €80/day; restore to €110 when stable
- Home Heating Oil Search: check impressions/spend from Apr 30 keywords — expected to ramp within 48 hours
- Conversion data: now accurate from Apr 30 onward. Reported CPL and conversion counts should appear ~4x lower than before
- Ad strength: rewritten ads will show updated ratings within 1-2 weeks
- 100+ ad groups still rated Poor in Brand & General Search — lower priority, address after hardware launches

---

## Notes

- Home Heating Oil Search keyword overlap: new geographic keywords (heating oil wexford etc.) overlap with Brand & General Search. Both campaigns will compete for these searches. Revisit once Home Heating Oil Search builds conversion history — may want to add as negatives to Brand & General at that point.
- Flo Gas error from Apr 28 corrected within same session: Kenny Fuels DOES stock Flo Gas products. Flo Gas negative was removed and keywords re-enabled as phrase match.
- All conversion data before Apr 30 is inflated 3-4x due to duplicate Primary conversion actions. Use Apr 30 onward as the baseline for accurate reporting.
