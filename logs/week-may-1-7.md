# Kenny Fuels - Week of May 1-7, 2026

## Campaign Performance Summary

### May 1-3 vs Apr 28-30 (Previous Period)

| Metric | Apr 28-30 | May 1-3 | Change |
|---|---|---|---|
| Impressions | 3,949 | 5,509 | +39% |
| Clicks | 670 | 516 | -23% |
| Cost | £421.27 | £419.59 | flat |
| Conversions | 6.60 | 3 | -55% |

### By Campaign

| Campaign | Period | Impressions | Clicks | CTR | Avg CPC | Cost | Conversions |
|---|---|---|---|---|---|---|---|
| Brand & General Search | Apr 28-30 | 2,518 | 540 | 21.45% | £0.58 | £315.77 | 3.05 |
| Brand & General Search | May 1-3 | 2,305 | 305 | 13.23% | £0.78 | £238.38 | 0 |
| Gas Bottle & Cylinders | Apr 28-30 | 1,352 | 111 | 8.21% | £0.92 | £102.36 | 3.55 |
| Gas Bottle & Cylinders | May 1-3 | 2,456 | 85 | 3.46% | £1.22 | £103.81 | 2 |
| Home Heating Oil Search | Apr 28-30 | 79 | 19 | 24.05% | £0.16 | £3.13 | 0 |
| Home Heating Oil Search | May 1-3 | 748 | 126 | 16.84% | £0.61 | £77.41 | 1 |

---

## What's Working

- **Gas Bottle phrase match:** Impressions up +82% (1,352 to 2,456). Phrase match pulling more volume. Cost held flat. Conversions continued (2 vs 3.55 prior).
- **Home Heating Oil Search scaling:** Impressions +847%, clicks +563%, first conversion recorded. At £0.61 CPC this is the most efficient traffic in the account.

---

## Issues Found

### CRITICAL
- **Brand ad group (Kenny Fuels) - 0 conversions May 1-3:** CTR dropped from 45% to 32%, CPC jumped from £0.19 to £0.33, conversions went from 3.05 to 0. Brand is the account's conversion engine.

### HIGH
- **Fuel Oil For Home Heating gutted:** Was #1 spending ad group Apr 28-30 (£111.49, 82 clicks). Dropped to £15.44, 9 clicks in May 1-3. Still ENABLED -- suppressed by something (possible overbroad negatives from last week).
- **Wexford geo CPCs exploded:** Wexford Home Heating Oil Services CPC £0.99 to £3.09 (+212%), Wexford Heating Oil Suppliers £1.79 to £3.63 (+103%), Heating Oil Prices Near Me Today £1.19 to £2.09 (+76%).

### MEDIUM
- **Gas Cylinder For Sale in Brand & General duplicating Gas Bottle campaign:** Spent £23.62 in May 1-3 with 0 conversions. Gas Bottle campaign is the one actually converting.

---

## Priority Actions - May 4, 2026

| # | Action | Status | Finding |
|---|---|---|---|
| P1 | Check search terms on Kenny Fuels brand ad group | DONE | Not a negative issue. Brand term IS getting clicks (161 clicks, £35.58) but 0 conversions. Likely conversion tracking or landing page issue. Also: General Negatives list NOT applied to any KF campaign. |
| P2 | Audit negatives -- find what throttled Fuel Oil For Home Heating | DONE | Not negatives. Home Heating Oil Search campaign scaled up (+847% impressions) and is now winning the same geo/oil queries that B&G Fuel Oil For Home Heating ad group used to serve. Internal cannibalization -- expected and correct behavior. |
| P3 | Set max CPC ceiling on Brand & General campaign | OPEN - MANUAL (API blocked) | Campaign is MAXIMIZE_CONVERSION_VALUE with no CPC ceiling. Wexford geo ad groups hitting £3.09-£3.63 CPCs with 0 conversions. API call blocked (portfolio strategy requires UI change). Fix in UI: Campaign Settings > Bidding > Maximize conversion value > tick "Set a maximum cost per click bid limit" > set £2.50. |
| P4 | Evaluate pausing Gas Cylinder For Sale in Brand & General | DONE | Confirmed: should pause. Ad group spent £23.62 May 1-3 with 0 conversions. Gas Bottle dedicated campaign is the one converting (2 conversions). Duplicate coverage, wasting B&G budget. |

---

## Structural Issues Found (May 4)

### CRITICAL: KF Campaigns Missing Negative Lists
All 3 KF Fuel campaigns only have "Fuel Campaigns - Hardware Exclusions" applied.
They are MISSING:
- **General Negatives** (photos, discount codes, job seekers, youtube, etc.)
- **Additional Negatives (14/01)** (price comparison terms, competitor names)

Result: irrelevant searches like "kevin building supplies", "building materials", "a142 mesh", "kenny fuels discount code", "kenny fuels photos" are all getting through into the brand ad group.

Recommended fix: Apply "General Negatives" to all 3 KF campaigns.

### Brand Ad Group Search Terms Needing Negatives (direct add)
Terms showing in Kenny Fuels brand ad group with no conversion intent:
- kevin building supplies (£7.76 CPC -- very expensive)
- a142 mesh near me
- kenny fuels discount code
- kenny fuels photos
- petrol station near me
- service station near me
- building materials, gravel, hardware, landscaping, decorative stone

### Fuel Oil For Home Heating - Competitors in Search Terms
Showing in search terms, need to be added as negatives:
- o neills fuels ltd
- burkes oil rathnew
- klass oil wicklow
- capitol oil
- corrib oil
- emo oil
- certa / certas / certa fuels
- texoil

---

## Changes Log

| Date | Action | Ad Group / Campaign | Detail |
|---|---|---|---|
| May 4 | FINDING | All KF campaigns | General Negatives and Additional Negatives lists NOT applied to KF campaigns |
| May 4 | FINDING | Kenny Fuels (brand ad group) | 0 conversions May 1-3 despite 161 clicks on brand term. Conversion tracking or landing page issue. |
| May 4 | FINDING | Fuel Oil For Home Heating | Throttled by Home Heating Oil Search campaign cannibalization, not negatives |
| May 4 | FINDING | Gas Cylinder For Sale | Duplicates Gas Bottle campaign, 0 conversions, recommend pause |
| May 4 | FINDING | Wexford geo ad groups | CPCs 100-200% higher, volume down -- likely auction competition from Home Heating Oil Search |
| May 4 | PAUSED | Gas Cylinder For Sale / Brand & General Search | Duplicate of Gas Bottle campaign; 0 conv May 1-3 while Gas Bottle campaign converted twice |
| May 4 | APPLIED SHARED LIST | All 3 KF Fuel campaigns | Applied "General Negatives" list -- blocks photos, discount codes, youtube, job terms etc. |
| May 4 | ADDED NEGATIVES (9) | Kenny Fuels brand ad group | Phrase negatives: kevin building supplies, a142 mesh, discount code, petrol station, service station, building materials, decorative stone, landscaping, gravel |
| May 4 | ADDED NEGATIVES (10) | Fuel Oil For Home Heating | Phrase negatives: o neills fuels, burkes oil, klass oil, capitol oil, corrib oil, emo oil, certas, texoil, atmos boilers, bunded tank |
| May 4 | FINDING | Conversion Tracking | Only 2 actions count toward conversions: "Calls from ads" (AD_CALL) and "Kenny Fuels - GA4 (web) purchase" (GA4). All other 15 actions are secondary/excluded. Other campaigns DID convert May 1-3 so tracking is live. Brand 0 conversions over 3 days likely statistical, but brand CPC spike (£0.19 to £0.33) suggests competitor may be bidding on "kenny fuels" brand terms. Monitor. |
| May 4 | OPEN - MANUAL | Brand & General -- CPC ceiling | Campaign on MAXIMIZE_CONVERSION_VALUE. No CPC ceiling set. Wexford geo hitting £3.09-£3.63 CPC. API blocked (portfolio strategy). Fix manually: Campaign Settings > Bidding > Maximize conversion value > Set max CPC bid limit > £2.50 |
| May 4 | PARKED FOR THURSDAY | P3 -- Wexford geo CPC ceiling / Brand & General bidding strategy | Decided against pausing Wexford ad groups (30-day data skewed by blocking negatives just removed today) and against switching to Target CPA (insufficient conversion volume, would reset learning period). Root cause of high CPCs may be the conflicting negatives now fixed. Review May 7/8 with a clean week of data -- if Wexford CPCs still elevated then, consider bid adjustment or Target ROAS in UI. |
| May 4 | REMOVED NEGATIVE | Brand & General Search (campaign-level) | Removed "prices" BROAD -- was blocking 7 active ad groups incl. Heating Oil Prices Near Me Today, Best Home Heating Oil Prices Wexford, Oil Prices Wexford |
| May 4 | REMOVED NEGATIVE | Brand & General Search (campaign-level) | Removed "price" BROAD (singular) -- was also blocking all price-related ad groups. Conflicting negatives warning still showed after first fix because this was still live. |
| May 4 | REMOVED NEGATIVE | Brand & General Search (campaign-level) | Removed "cheapest" BROAD -- was blocking Cheapest Oil Prices Wexford ad group |
| May 4 | CHANGED MATCH TYPE | Brand & General Search (campaign-level) | "top oil" changed BROAD to EXACT -- competitor brand still blocked, Top Heating Oil Supplier Wicklow ad group now unblocked |
| May 4 | REMOVED FROM SHARED LIST | Fuel Campaigns - Hardware Exclusions | Removed "firewood" BROAD -- was blocking all firewood ad groups (firewood logs for sale, firewood bags for sale, places to buy firewood, kiln dried oak firewood for sale). Kenny Fuels sells firewood so this was incorrect. |
| May 5 | FINDING | Brand & General Search | Search terms audit May 1-4: 9 problematic queries identified. Irrelevant: kevin building supplies, zf 6 speed oil (motor oil), 20w50 (lubricant), atmos boilers ireland (boiler service), kiln dried shavings (wrong product). Competitor: wicklow wood fuels. Price terms (re-confirmed already blocked May 4): cheapest, price, prices. |
| May 5 | ADDED NEGATIVES (6) | Brand & General Search (campaign-level) | Broad: kevin, zf, 20w50, boilers. Phrase: kiln dried shavings, wicklow wood fuels. |
| May 5 | ERROR CORRECTED | Brand & General Search (campaign-level) | price, prices, cheapest incorrectly re-added as BROAD negatives then immediately removed. These were already removed May 4 as they blocked Heating Oil Prices Near Me Today, Best Home Heating Oil Prices Wexford, Oil Prices Wexford, and Cheapest Oil Prices Wexford ad groups. Net effect: zero -- error caught and reversed same session. |
| May 5 | ADDED KEYWORD | Home Heating Oil Search -- Ad Group: Home Heating Oil | Added "kero heating oil" (phrase match). 170 searches/month in Ireland. Informal Irish term for kerosene heating oil, not yet in account. |
| May 5 | CAMPAIGN CREATED | KF - Hardware | Composite Decking (new) | New Search campaign built. Budget: €15/day, Maximise Clicks, targeting Wexford/Wicklow/Carlow. 18 phrase match keywords. Hardware Campaigns - Fuel Exclusions negative list applied. Campaign ID: 23823083722. |
| May 5 | AD GROUPS CREATED (4) | KF - Hardware | Composite Decking | Built 4 themed ad groups: Composite Decking - General (4 keywords), Composite Decking - Price & Buy (5 keywords), Composite Decking - Geo (4 keywords), Composite Decking - Boards & Planks (5 keywords). Each ad group has 15 headlines, 4 descriptions. Overlapping keywords removed from General ad group. |
| May 5 | SITELINKS ADDED (15) | KF - Hardware | Composite Decking (campaign-level) | Added 15 sitelinks: Composite Decking Boards, Premium Decking Range, Composite Fencing, Premium Cladding, Domestic Products, Hardware Products, Acoustic Wall Panels, Safety Equipment, Workwear Ireland, Power & Hand Tools, Building Products, Gardening & Landscaping, Gardening Tools, General Hardware, Animal Feed & Supplies. |
| May 5 | GA4 MCP CONNECTED | Account | Set up GA4 MCP access with josette@outposter.com.au. Property: Kenny Fuels - GA4, ID: 396621665. Google Analytics Data API and Admin API enabled in Google Ads MCP project. |
| May 5 | FINDING | Conversion Tracking | GA4 shows 16 conversions May 1-5 from Brand & General but Google Ads shows 0. Root cause: view_item incorrectly marked as key event (12 of 16 "conversions" were product page views). Also: Purchase_2 firing 84 times with €0 revenue -- duplicate/broken tag. |
| May 5 | FIXED | GA4 Key Events | Unmarked view_item as key event -- was inflating all conversion counts. Unmarked Purchase_2 (84 fires, €0 revenue -- duplicate of purchase). Unmarked ads_conversion_Checkout_1 (229 fires, €0 -- duplicate of begin_checkout). Unmarked ads_conversion_Shopping_Cart_1 (32 fires, €0 -- duplicate of add_to_cart). Unmarked ads_conversion_add_to_cart (0 fires -- dead tag). |
| May 5 | FINDING | Conversion Tracking | Actual purchases Apr 1-May 5: 40 real purchase events totalling €13,798 revenue. Only 2 actual purchases recorded in Brand & General May 1-5. Google Ads showing 0 because GA4 import attribution may differ -- monitor May 7-8 with clean key events. |
| May 5 | PENDING | Broken GTM Tags | add_payment_info, click_to_call, ruler_call all showing No stream data in GA4. Tags broken -- requires GTM access from Graphedia to fix. |
| May 5 | FINDING | Sessions Discrepancy | Investigated 440 Google Ads clicks vs 49 GA4 sessions for Brand & General May 1-5. Landing pages confirmed: no redirect issues, gclid preserved on all 6 final URLs. Root cause: two GA4 measurement IDs firing on every page -- G-0RM5FH1MST (PixelYourSite plugin) and G-BMD8SXLKC0 (direct script). GA4 property 396621665 linked to Google Ads (confirmed) but only capturing ~11% of sessions. Missing sessions likely going to the other GA4 property. |
| May 5 | SENT TO CLIENT | Graphedia Consolidated Request | Drafted and sent consolidated tracking fix request to client for forwarding to Graphedia. Items: (1) identify which GA4 measurement ID belongs to property 396621665 and remove the duplicate tag. (2) fix Contact Us Form and Book Appointment GTM tags. Client to forward to Graphedia -- reply pending. |
| May 6 | FINDING | Brand & General Search | 30-day conversion audit: campaign converting regularly Apr 6-30 (1-12 conv/day, up to €3,600 value). Complete conversion cliff from May 1 -- 0 conversions every day May 1-5. Coincides with CPC spike from €0.07-0.24 to €0.60-0.85. Maximize Conversion Value algorithm bidding aggressively with no conversion signal. Historical April conversions partially inflated by view_item key event (now fixed). |
| May 6 | FINDING | Brand & General Search | May 5 ad group breakdown: Kenny Fuels brand (80 clicks, €0.17 CPC) healthy. Non-brand geo/price ad groups driving high CPCs: Home Heating Oil Carlow €2.08, Firewood Logs For Sale €1.93, Wexford Heating Oil Suppliers €1.53, Heating Oil Prices Near Me Today €1.26. CPCs stable (not spiralling) -- €80/day budget acting as natural ceiling. |
| May 6 | CHANGED | Brand & General Search -- Bidding Strategy | Switched from portfolio Maximize Conversion Value to standard campaign-level Maximize Conversion Value. Required to attempt CPC ceiling -- portfolio strategy was blocking the option. Confirmed via API: campaign.bidding_strategy_type = MAXIMIZE_CONVERSION_VALUE (standard). |
| May 6 | BLOCKED | Brand & General Search -- CPC Ceiling | Attempted to set €2.50 max CPC ceiling via UI and API. UI: option not available in new Google Ads interface. API: "The operation is not allowed for the given context." CPC ceiling cannot be set on this campaign at this time. CPCs stable ~€0.61 avg (May 5), €80/day budget is the practical ceiling. No further bidding changes until May 7-8 review. |
| May 6 | NO CHANGE | Brand & General Search -- Customer Acquisition | Setting confirmed as "Bid equally for new and existing customers." Left unchanged -- requires clean conversion data to be useful. Review after Graphedia fixes tracking. |
| May 6 | PERFORMANCE CHECK | KF - Hardware | Composite Decking | May 5-6 performance: 11 clicks, 46 impressions, €18.21 spend. All 4 ad groups live. Boards & Planks leading (7 clicks, 21% CTR, €1.63 CPC). Price & Buy 33% CTR. Geo 50% CTR (small sample). General quiet as expected (most competitive terms). All 18 keywords phrase match, no overlap confirmed. CPCs €1.46-1.87 -- reasonable for this category. No issues. Monitor for 2-3 weeks. |
| May 7 | BUDGET REDUCED | Brand & General Search | €80/day to €50/day. Off-season demand has dropped -- heating oil season ended. Budget redirected to summer campaigns. |
| May 7 | BUDGET REDUCED | Home Heating Oil Search | €50/day to €25/day. Bulk orders have stopped for the season. Emergency and commercial phone calls still coming in, hence maintaining at reduced level rather than pausing. |
| May 7 | BUDGET INCREASED | Gas Bottle & Cylinders | €35/day to €50/day. BBQ season beginning. Increased budget to capture summer demand. |
| May 7 | BUDGET INCREASED | KF - Hardware | Composite Decking | €15/day to €25/day. Early performance strong (€1.46-1.87 CPC, healthy CTRs). Additional budget to support continued data collection. |
| May 7 | ADDED KEYWORDS (7) | Gas Bottle & Cylinders -- Gas Cylinders ad group | Phrase match BBQ/summer keywords: "bbq gas ireland", "bbq gas cylinder ireland", "patio gas ireland", "calor gas bbq", "propane gas bbq", "gas for bbq near me", "bbq gas bottle near me". Targets summer BBQ demand. |
| May 7 | PAUSED (42 AD GROUPS) | Brand & General Search | Paused all heating oil, coal, solid fuel, and briquettes ad groups for off-season. Kept active: brand (Kenny Fuels), emergency, gas/LPG/propane/butane, firewood/kiln dried logs, lubricants. Off-season ad groups to be re-enabled September when heating oil season resumes. |
| May 7 | REMOVED KEYWORDS (2) | Brand & General Search | Removed competitor brand keywords from positive keyword slots: "flogas near me" (Gas Suppliers Near Me ad group) and "new line oil wexford" (Wexford Home Heating Oil Services ad group). Both were paused ad groups but competitor keywords in positive slots are incorrect regardless. Negatives for flogas and new line oil remain in place. |
| May 7 | DISMISSED | Gas Bottle & Cylinders | Dismissed Google recommendation to remove "forklift" BROAD negative (+0.7% optimisation score). Research confirmed: all 3 blocked keywords have 0 search volume in Ireland (DataForSEO verified). Kenny Fuels does not sell forklift gas cylinders -- product range is domestic/BBQ only (6kg and 47kg propane). Negative is correct. |
| May 7 | RESTRUCTURED | Brand & General Search | Ad group review following off-season pauses. 26 gas/LPG ad groups paused (duplicating Gas Bottle & Cylinders campaign -- 895 impressions, 49 clicks, €46 cost, 0 conversions in 30 days). 20 firewood SKAGs consolidated into 2 ad groups: Kiln Dried Logs (16 phrase keywords, 15 headlines, 4 descriptions) and Firewood (9 phrase keywords, 15 headlines, 4 descriptions). |
| May 7 | REMOVED KEYWORDS (3) | Gas Bottle & Cylinders -- Gas Cylinders ad group | Removed 3 forklift gas cylinder keywords found in positive keyword slots: "forklift gas cylinders", "gas for forklifts", "forklift lpg gas". These were blocking the forklift BROAD negative. Removed as Kenny Fuels does not stock forklift cylinders. |
| May 7 | FIXED MATCH TYPES | Brand & General Search -- Emergency Heating Oil Near Me | Changed "emergency heating oil near me" from BROAD to PHRASE. BROAD gives Google too much latitude on Maximize Conversion Value with no conversion signal. |
| May 7 | FIXED MATCH TYPES | Brand & General Search -- Emergency Oil Delivery Near Me | Changed "emergency oil delivery near me" and "24 hour oil delivery near me" from BROAD to PHRASE. |
| May 7 | REMOVED KEYWORD | Brand & General Search -- Lubricants For Sale | Removed "lubricants for sale" BROAD. PHRASE version already existed in same ad group -- duplicate removed. |
| May 7 | REMOVED KEYWORD | Brand & General Search -- Kenny Fuels (brand ad group) | Removed "kenny fuels" BROAD. PHRASE and EXACT match versions already exist in the same ad group -- BROAD was redundant. |
| May 7 | REMOVED KEYWORDS (9) | Brand & General Search -- Kenny Fuels (brand ad group) | Removed 9 legacy non-brand positive keywords: building materials, landscaping, discount code, service station, decorative stone, gravel, petrol station, a142 mesh, kevin building supplies. These were pre-existing SKAG-era keywords in the brand ad group that were already blocked by the negatives added May 4. Removed to clean up the ad group properly. |
| May 7 | REPLACED RSA | Brand & General Search -- Emergency Heating Oil Near Me | Removed 2 old RSAs (6 headlines each, generic heating oil descriptions unrelated to emergency intent). Created 1 new RSA: 15 headlines, 4 emergency-specific descriptions, pinned H1 "Emergency Heating Oil". Final URL: /home-heating-oil-wexford-carlow-wicklow/. |
| May 7 | REPLACED RSA | Brand & General Search -- Emergency Oil Delivery Near Me | Removed 2 old RSAs (6 headlines each, generic descriptions). Created 1 new RSA: 15 headlines, 4 emergency oil delivery-specific descriptions, pinned H1 "Emergency Oil Delivery". Final URL: /home-heating-oil-wexford-carlow-wicklow/. |
| May 7 | REPLACED RSA | Brand & General Search -- Lubricants For Sale | Removed 2 old RSAs (5 headlines each, heating oil/coal/firewood descriptions -- completely wrong product). Created 1 new RSA: 15 headlines covering engine oil, hydraulic oil, agricultural and motor lubricants. 4 lubricants-specific descriptions. Pinned H1 "Lubricants For Sale Ireland". Final URL: /product-category/lubricants/page/2/. |
| May 8 | REVIEWED | Brand & General Search -- Conversions | Review of May 1-7 conversion data. Still 0 throughout the week (0.11 fractional on May 6 -- modelled attribution, not a real purchase). Root cause unchanged: GA4 tracking not fixed by Graphedia. CPCs trending down positively: €0.85 (May 1) → €0.60 (May 4) → €0.52 (May 7). Negative fix from May 4 is working. No action -- waiting on Graphedia. |
| May 8 | REVIEWED | Brand & General Search -- Wexford geo CPCs | Wexford-specific ad groups (Wexford Home Heating Oil Services, Wexford Heating Oil Suppliers, etc.) all paused May 7 as part of off-season restructure. Issue resolved by removal. Remaining active ad groups: Kenny Fuels brand €0.20 CPC, Emergency groups €0.81-€1.09, Lubricants €0.79, Firewood €2.93 (new group, day 1 -- expected high, monitoring). No action required on Wexford. |
| May 8 | REVIEWED | KF - Hardware -- Composite Decking (3-day check) | Boards & Planks leading: impressions scaling (31 → 30 → 94 over 3 days), clicks up to 17 on May 7, CPC declining €1.63 → €1.20. General and Price & Buy active, CPCs trending down. Geo quiet. No conversions yet -- too early. On track. Next review: ~May 22 (2-3 week mark). |
| May 8 | CHASED | Graphedia tracking fix | 3 days since consolidated fix request sent to client (May 5). No update received. Client needs to re-chase Graphedia urgently. Until fixed, conversion data for Brand & General is unreliable and algorithm cannot optimise. |
| May 8 | CONVERSION AUDIT | Account | Full conversion tracking audit across Google Ads (24 actions) and GA4 (22 events). Issues found: Smart Goal (UA, dead) still primary; Purchase_2_GTM_GA4 broken duplicate; begin_checkout and add_to_cart still key events in GA4; Contact Us Form, Book Appointment, Click to Call GTM tags all broken; website call tracking (forwarding number) not set up -- calls from website completely untracked. |
| May 8 | MANUAL REQUIRED | Google Ads -- Smart Goal | Cannot demote via API (UA type immutable). Needs manual UI fix: Goals > Conversions > Smart Goal > Edit > uncheck Include in Conversions. Demotes from primary to secondary. |
| May 8 | MANUAL REQUIRED | GA4 -- begin_checkout & add_to_cart key events | Both still marked as key events. Need to unmark in GA4 UI: Admin > Property > Key Events > toggle off begin_checkout and add_to_cart. Only purchase should remain as key event. |
| May 8 | ADDED TO GRAPHEDIA REQUEST | Website call tracking | Google Ads forwarding number not set up. When someone arrives from a Google Ad and calls the phone number on the website, that call is completely invisible to Google Ads. Graphedia needs to install the Google phone snippet on the website to enable dynamic number replacement for Google Ads visitors. Added to Graphedia email. |
| May 8 | ADDED TO GRAPHEDIA REQUEST | Form differentiation | 257 form_submits firing in GA4 Apr-May but no way to tell which form (Contact vs Booking vs Quote). Graphedia needs to add form ID differentiation to GTM tags so each form type is tracked separately. Added to Graphedia email. |
| May 8 | FIXED | Brand & General Search -- Kiln Dried Logs RSA | Was DISAPPROVED: "Destination not working". Old URL /kiln-dried-logs/ returned 404. Checked website sitemap -- correct URL confirmed as /product-category/kiln-dried-firewood-logs/. Removed old RSA, recreated with correct URL (same 15 headlines, 4 descriptions). Ad re-entered review queue. |
| May 8 | MONITORING | Brand & General -- Firewood ad group CPC | New consolidated Firewood ad group (created May 7) showing €2.93 avg CPC on first day (5 clicks). High CPC expected on day 1 as algorithm explores. Monitor over next 7 days to confirm CPCs settle. If still above €2.00 by May 15, review keyword match types or add negatives. |

---

## Weekly Notes

### 1. Account Hygiene -- Negative Keywords & Structural Fixes

A full audit of negative keyword lists across all campaigns identified several issues that were suppressing ad groups and allowing irrelevant traffic through.

**Negative lists applied:**
- Applied "General Negatives" shared list to all 3 KF Fuel campaigns -- this list was missing entirely. Blocks photos, discount codes, YouTube searches, job seekers, and other non-commercial queries.
- Removed "firewood" BROAD from the Fuel Campaigns - Hardware Exclusions shared list. Kenny Fuels sells firewood, so this was incorrectly blocking all firewood ad groups.

**Conflicting campaign-level negatives removed (Brand & General):**
- "price" and "prices" BROAD were blocking 7 active ad groups including Heating Oil Prices Near Me Today, Best Home Heating Oil Prices Wexford, and Oil Prices Wexford.
- "cheapest" BROAD was blocking Cheapest Oil Prices Wexford.
- "top oil" BROAD was blocking Top Heating Oil Supplier Wicklow -- changed to EXACT so the competitor brand (Top Oil) remains blocked while the ad group is unblocked.

**New negatives added:**
- 9 phrase negatives added to Kenny Fuels brand ad group: kevin building supplies, a142 mesh, discount code, petrol station, service station, building materials, decorative stone, landscaping, gravel.
- 10 competitor phrase negatives added to Fuel Oil For Home Heating: o neills fuels, burkes oil, klass oil, capitol oil, corrib oil, emo oil, certas, texoil, atmos boilers, bunded tank.
- 6 campaign-level negatives added to Brand & General Search following May 1-4 search terms audit: kevin, zf, 20w50, boilers (broad); kiln dried shavings, wicklow wood fuels (phrase).

**Ad group paused:**
- Gas Cylinder For Sale (Brand & General) paused. Duplicate of Gas Bottle & Cylinders campaign which is the one actually converting. Spent €23.62 May 1-3 with 0 conversions.

**Keyword added:**
- "kero heating oil" (phrase match) added to Home Heating Oil Search. 170 searches/month in Ireland -- informal Irish term for kerosene heating oil that was not in the account.

---

### 2. New Campaign Launch -- KF Hardware | Composite Decking

Campaign built and launched May 5 as planned.

**Setup:**
- Budget: €15/day | Bidding: Maximise Clicks | Targeting: Wexford, Wicklow, Carlow
- 4 themed ad groups: General, Price & Buy, Geo, Boards & Planks
- 18 phrase match keywords, no overlap between ad groups
- 15 campaign-level sitelinks added
- Hardware Campaigns - Fuel Exclusions negative list applied

**Early performance (May 5-6):**

| Ad Group | Clicks | CTR | Avg CPC | Spend |
|---|---|---|---|---|
| Boards & Planks | 7 | 21.2% | €1.63 | €11.43 |
| Price & Buy | 2 | 33.3% | €1.72 | €3.45 |
| Geo | 1 | 50.0% | €1.46 | €1.46 |
| General | 1 | 20.0% | €1.87 | €1.87 |

Strong CTRs across all ad groups on day one. Boards & Planks leading volume as expected. CPCs in the €1.46-1.87 range -- reasonable for composite decking in Ireland. Review after 2-3 weeks.

---

### 3. Conversion Tracking Investigation -- Brand & General 0 Conversions

Brand & General has recorded 0 conversions since May 1 despite 440+ clicks. A full investigation was conducted across landing pages, auto-tagging, GA4, and bidding.

**What was ruled out:** Landing page redirects (all 6 final URLs preserve gclid), auto-tagging (confirmed enabled), GA4 link to Google Ads (confirmed active since July 2023).

**Root cause identified -- duplicate GA4 tags:**
Two GA4 measurement IDs are firing on every page of the website: G-0RM5FH1MST (PixelYourSite plugin) and G-BMD8SXLKC0 (direct script). The property linked to Google Ads (396621665) is only capturing 11% of clicks as sessions. The remaining 89% of sessions go to the other GA4 property, meaning Google Ads cannot attribute conversions for those clicks even when a purchase happens.

**GA4 key events cleaned up:**
Four incorrect key events removed that were inflating conversion counts: view_item (product page views counted as conversions), Purchase_2 (duplicate tag, €0 revenue), ads_conversion_Checkout_1 (duplicate of begin_checkout), ads_conversion_Shopping_Cart_1 (duplicate of add_to_cart). Remaining key events: purchase, begin_checkout, add_to_cart.

**Fix required from Graphedia (request sent to client May 5):**
1. Confirm which GA4 measurement ID belongs to property 396621665 and remove the duplicate tag
2. Fix Contact Us Form and Book Appointment conversion tags in GTM (GTM-5Z97JLX, GTM-TQR899VB)

**Note:** The 0 conversions in Google Ads does not mean 0 actual purchases. GA4 shows €137 in purchase revenue attributed to Brand & General sessions May 1-5. Conversions are happening but Google Ads cannot record them until the tracking is fixed.

---

### 4. Deep Dive -- Why Brand & General Conversions Dropped

A full March-May analysis was conducted to understand the conversion decline in Brand & General Search. Three overlapping factors were identified.

**Factor 1: Seasonal demand decline (primary cause)**

Brand & General was the account's top revenue driver during the heating oil season:

| Period | Avg Daily Conversions | Avg Daily Revenue | Avg CPC |
|---|---|---|---|
| March 1-15 | 15-57 | €1,000-7,900 | €0.13 |
| April 1-15 | 2-12 | €110-3,600 | €0.10 |
| April 16-27 | 0-8 | €0-1,560 | €0.12 |
| April 28-30 | 0-2 | €0-247 | €0.53 |
| May 1-7 | 0 | €0 | €0.68 |

Heating oil is a winter/early spring product in Ireland. The conversion decline began April 16 -- two and a half weeks before any changes were made to the account. March 2 was the peak of the season (57 conversions, €7,901 revenue in a single day). By May, bulk household heating oil orders have effectively stopped for the season.

**Factor 2: Algorithm reacting to the seasonal drop (CPC spiral)**

The Maximize Conversion Value bidding strategy requires consistent conversion data to bid efficiently. As conversions dropped through April, the algorithm entered exploration mode and began bidding aggressively to find conversions that were no longer there. The CPC inflection happened April 26 -- before any of our changes:

- April 25: €0.12 CPC, 8.27 conversions
- April 26: €0.23 CPC, 0 conversions
- April 28: €0.38 CPC, 2 conversions
- April 29: €0.75 CPC, 0 conversions (240 clicks -- algorithm in full exploration)
- May 1+: €0.60-0.85 CPC, 0 conversions

CPCs 6x'd in under a week driven entirely by the algorithm, not account changes.

**Factor 3: Tracking issue amplifying the decline**

The duplicate GA4 tag issue (89% session loss) was present throughout March and April. During peak season, purchase volume was high enough that even 11% of properly tracked sessions contained conversions. As seasonal volume dropped in May, that same 11% stopped reliably containing purchases -- so Google Ads records 0, even though GA4 still shows purchase revenue happening.

**Did our changes cause the decline?**

No. The data is clear: the conversion cliff started May 1, our first changes were May 4. Every change made was a structural fix to pre-existing problems. Notably, the conflicting negatives (price, prices, cheapest BROAD) were blocking high-intent price ad groups throughout the entire March-April peak season -- the campaign was converting strongly despite those blocks. Removing them was correct and would have made the peak even stronger had it been done earlier.

**Why is Home Heating Oil Search still converting while Brand & General is not?**

These campaigns convert through different mechanisms:

| Campaign | Conversion type | Value per conv | Tracking method |
|---|---|---|---|
| Brand & General (April) | Web purchase -- bulk orders | €150-700 | GA4 import (needs gclid) |
| Home Heating Oil Search (May) | Phone call from ad | €1 (default) | AD_CALL (no GA4 needed) |

Home Heating Oil Search is generating phone call conversions -- people clicking an ad and calling directly. This tracking works independently of GA4 and gclid. Some demand for heating oil continues year-round (emergency orders, commercial customers, people who ran out) but these are smaller, urgent orders where people call rather than order online. Brand & General's high-value web purchase conversions represent planned bulk orders -- those are seasonal and have stopped for the year.

**Recommendation:** Expect Brand & General web purchase conversions to remain near zero through May-August and recover naturally in September-October when the heating oil season resumes. Priority for now is fixing the GA4 tracking (Graphedia) so the algorithm has a clean signal when demand returns, and ensuring hardware ad groups (gas, lubricants, composite decking) carry the account through the off-season.

---

### 5. Brand & General -- Bidding Update (May 6)

**30-day review:** Brand & General converted consistently April 6-30. Complete stop from May 1, coinciding with a CPC increase from €0.07-0.24 to €0.60-0.85. The Maximize Conversion Value algorithm has been bidding aggressively with no conversion signal to work from.

**Change made:** Campaign switched from portfolio Maximize Conversion Value to standard campaign-level Maximize Conversion Value. The algorithm now optimises on this campaign's data only.

**CPC ceiling:** Attempted to set a €2.50 max CPC cap. Not available in the current Google Ads UI and blocked via API. The €80/day daily budget is the practical ceiling. CPCs are stable, not spiralling. No further bidding changes until May 7-8 review.

---

### 6. Off-Season Repositioning -- May 7

With the heating oil season now closed, the account was repositioned for summer on May 7.

**Budget reallocation:**

| Campaign | Old Budget | New Budget | Reason |
|---|---|---|---|
| Brand & General Search | €80/day | €50/day | Heating oil season ended, primary driver inactive |
| Home Heating Oil Search | €50/day | €25/day | Bulk orders stopped; emergency/commercial calls continuing |
| Gas Bottle & Cylinders | €35/day | €50/day | BBQ season starting, higher summer demand |
| Composite Decking | €15/day | €25/day | Strong early CTRs, additional budget to support data collection |

Total daily budget unchanged at €150/day. Spend redistributed from off-season to active campaigns.

**BBQ/summer keywords added to Gas Bottle & Cylinders:**

7 phrase match keywords added to the Gas Cylinders ad group targeting summer BBQ demand:
- bbq gas ireland
- bbq gas cylinder ireland
- patio gas ireland
- calor gas bbq
- propane gas bbq
- gas for bbq near me
- bbq gas bottle near me

**Heating oil ad groups paused in Brand & General (42 groups):**

All heating oil, coal, solid fuel, and briquettes ad groups paused for the off-season. Budget in Brand & General will now concentrate on the ad groups still relevant year-round: Kenny Fuels brand, emergency oil delivery, gas/LPG/propane/butane, firewood/kiln dried logs, and lubricants.

Ad groups to re-enable: September 2026, ahead of the heating oil season resuming.

### 7. Brand & General -- Ad Group Restructure & RSA Overhaul (May 7)

#### Gas / LPG Ad Groups (26 paused)
26 ad groups covering gas cylinders, LPG, propane, and butane were paused. These groups had 895 impressions, 49 clicks, €46 cost and 0 conversions over 30 days -- duplicating the Gas Bottle & Cylinders campaign which is the one converting. Budget previously split across these groups now concentrates on the remaining active ad groups.

#### Firewood Consolidation (20 SKAGs → 2 ad groups)
20 single-keyword firewood ad groups replaced with 2 consolidated ad groups. Both now have 15 headlines and 4 descriptions.

#### Emergency & Lubricants RSAs -- Replaced

The 3 remaining legacy ad groups (Emergency Heating Oil Near Me, Emergency Oil Delivery Near Me, Lubricants For Sale) had RSAs with only 5-6 headlines each and descriptions referencing the wrong products (heating oil/coal/firewood in a lubricants ad group). All replaced with full 15-headline RSAs.

---

**Emergency Heating Oil Near Me** -- [kennyfuels.ie/home-heating-oil-wexford-carlow-wicklow/](https://www.kennyfuels.ie/home-heating-oil-wexford-carlow-wicklow/)

| # | Headline | Pin |
|---|---|---|
| 1 | Emergency Heating Oil | H1 (pinned) |
| 2 | Urgent Delivery Available | |
| 3 | Run Out Of Heating Oil? | |
| 4 | Fast Heating Oil Delivery | |
| 5 | Home Heating Oil Wexford | |
| 6 | Heating Oil Wicklow & Carlow | |
| 7 | 2-3 Day Delivery Service | |
| 8 | Order Online Anytime | |
| 9 | Kenny Fuels Emergency Oil | |
| 10 | Competitive Emergency Prices | |
| 11 | Trusted Local Supplier | |
| 12 | Free Quote In Minutes | |
| 13 | Don't Get Left In The Cold | |
| 14 | On-Time Delivery Guaranteed | |
| 15 | Quality Heating Oil Supply | |

| # | Description |
|---|---|
| 1 | Ran out of heating oil? Order from Kenny Fuels for fast delivery across Wexford & Wicklow. |
| 2 | Emergency heating oil delivered to Wexford, Wicklow and Carlow. Free quote online. |
| 3 | Quality heating oil, 2-3 day delivery. Don't be left in the cold. Kenny Fuels. |
| 4 | Trusted heating oil supplier for Wexford, Wicklow & Carlow. Competitive prices. |

---

**Emergency Oil Delivery Near Me** -- [kennyfuels.ie/home-heating-oil-wexford-carlow-wicklow/](https://www.kennyfuels.ie/home-heating-oil-wexford-carlow-wicklow/)

| # | Headline | Pin |
|---|---|---|
| 1 | Emergency Oil Delivery | H1 (pinned) |
| 2 | 24 Hour Oil Enquiries | |
| 3 | Urgent Oil Delivery Ireland | |
| 4 | Run Out Of Heating Oil? | |
| 5 | Order Oil Delivery Online | |
| 6 | Wexford & Wicklow Delivery | |
| 7 | Heating Oil Carlow Delivery | |
| 8 | Fast Oil Delivery Service | |
| 9 | Kenny Fuels Oil Delivery | |
| 10 | 2-3 Day Delivery Available | |
| 11 | Trusted Local Fuel Supplier | |
| 12 | Competitive Oil Prices | |
| 13 | Free Quote In Minutes | |
| 14 | Order Online Anytime | |
| 15 | Home Heating Oil Supply | |

| # | Description |
|---|---|
| 1 | Need oil urgently? Kenny Fuels delivers heating oil fast to Wexford, Wicklow & Carlow. |
| 2 | Reliable oil delivery when you need it most. 2-3 day service, free quote online. |
| 3 | Ran out of oil? Order from Kenny Fuels for on-time delivery across Wexford & Wicklow. |
| 4 | Heating oil delivery across Wexford and Wicklow. Trusted, competitive prices. |

---

**Lubricants For Sale** -- [kennyfuels.ie/product-category/lubricants/](https://www.kennyfuels.ie/product-category/lubricants/page/2/)

| # | Headline | Pin |
|---|---|---|
| 1 | Lubricants For Sale Ireland | H1 (pinned) |
| 2 | Engine Oil & Lubricants | |
| 3 | Motor & Hydraulic Oils | |
| 4 | Agricultural Lubricants | |
| 5 | Buy Lubricants Online | |
| 6 | Kenny Fuels Lubricants | |
| 7 | Lubricants Delivered Fast | |
| 8 | Wexford & Wicklow Delivery | |
| 9 | Bulk Lubricant Orders | |
| 10 | Competitive Lubricant Prices | |
| 11 | Free Quote In Minutes | |
| 12 | Order Lubricants Online | |
| 13 | Trusted Local Supplier | |
| 14 | Wide Range In Stock | |
| 15 | Quality Oil Products | |

| # | Description |
|---|---|
| 1 | Kenny Fuels stocks engine oils, hydraulic oils and lubricants. Delivered to your door. |
| 2 | Agricultural and motor lubricants available online. Fast delivery Wexford & Wicklow. |
| 3 | Wide range of lubricants in stock. Competitive prices, bulk orders welcome. Free quote. |
| 4 | Order lubricants online from Kenny Fuels. Quality products, fast local delivery. |

---

### Open Items for Review May 7-8 -- Reviewed May 8

| # | Item | Status | Outcome |
|---|---|---|---|
| P1 | Graphedia tracking fix | STILL PENDING | No update from Graphedia after 3 days. Client needs to re-chase. Blocking conversion data for Brand & General. |
| P2 | Brand & General conversions | REVIEWED May 8 | Still 0 conversions May 1-7 (one 0.11 fractional on May 6 -- not a real purchase). Tracking not fixed. CPCs trending down: €0.85 → €0.52. Negative fix working. No action until tracking resolved. |
| P3 | Wexford geo CPCs | CLOSED May 8 | All Wexford ad groups paused off-season May 7. Issue resolved. Remaining active CPCs normal. |
| P4 | Composite Decking | REVIEWED May 8 -- monitor to May 22 | Boards & Planks scaling well (impressions 31→94 in 3 days, CPC declining). On track. Next review ~May 22. |

### Monitoring Schedule

| Item | Next Check | What to Look For |
|---|---|---|
| Graphedia tracking fix | Ongoing -- chase weekly | GA4 duplicate tag removed, conversion data flowing into Google Ads |
| Brand & General conversions | Week of May 14 | Any conversions recording once tracking fixed |
| Firewood ad group CPC | May 15 | CPC should settle below €2.00 as algorithm learns; if still above, review |
| Gas Bottle & Cylinders budget | May 15 | Confirm hitting €50/day cap consistently as BBQ season builds -- increase if so |
| Composite Decking full review | ~May 22 | 2-3 week data: CPCs, CTR, any conversions -- decide on next hardware campaign |
| Next hardware campaign build | After May 22 review | Composite Fencing or Cladding -- only if Composite Decking data is positive |
| Heating oil ad groups re-enable | September 2026 | Re-enable all 42 paused heating/coal/solid fuel ad groups ahead of new season |

### Next Steps

- Urgent: Client to re-chase Graphedia on tracking fix (3 days outstanding, blocking conversion optimisation)
- May 15: Check Firewood CPC and Gas Bottle budget utilisation
- May 22: Composite Decking 3-week review -- decide on next hardware campaign
- September: Re-enable heating oil/coal/solid fuel ad groups in Brand & General ahead of new heating season
