# Valuation, Price, and Rating Rules

This is the single source of rating definitions. Ratings measure **absolute prospective total return over the stated horizon**, not expected outperformance against an index. These are internal research conventions, not universal industry standards or calibrated guarantees. Explicit user/institution rules supersede them with a disclosed mapping.

Do not equate rating letters across source reports or institutions. Compare their meanings, return definitions, horizons and risk rules; disclose any mapping. Display one main rating under V05, its meaning, reference return, horizon, and any risk adjustment. Scenario or sensitivity rating spans are diagnostic outputs, never the main recommendation.

## V01 Price and Time Basis

**Inputs:** Security identity, observed price P0 and timestamp/status, currency, research cutoff, horizon H, target date, expected per-share distributions D, shares, and capital structure.

**Analysis:** Default H to 12 months. Identify both the target date and earnings period used for valuation. Keep price/dividends/target in the same share class, currency, and split-adjusted units. Unless otherwise requested, report nominal pre-tax total return excluding fees and dividend reinvestment. Apply information-freshness.md: a material announcement after the selected close requires a post-event quote when verifiable, with trading-session limitations disclosed; otherwise the old-price calculation is explicitly conditional. Refresh the price and material events before delivery and recompute affected outputs. Missing reliable price allows conditional entry ranges, not a fabricated current rating.

**Outputs:** Explicit pricing basis and source, distinguishing current fair value from a future target price.

## V02 Method Selection, Parameter Evidence, and Value Bridge

**Inputs:** M03's operating-stage/business assessment and research priorities, M08 forecasts, F05–F07 cash/investment/funding analysis, capital structure, and dated market/comparable evidence.

### Select roles before interpreting valuation outputs

No valuation method is mandatory for all companies or size categories. Choose the method that best explains the business with supportable inputs, then an informative supporting test where available. Connect operating evidence → earnings/cash forecast → valuation assumptions → price/return logic. State why a method is primary, supporting, conditional only, or not applicable; unavailable evidence must not be invented to complete a model.

| Candidate tool | When it can be useful | Evidence and limitations to resolve |
|---|---|---|
| Forward / normalized PE | Meaningful, reasonably forecastable attributable earnings and informative historical/peer pricing | EPS period/definition, recurring adjustments, growth durability, cash conversion, capital needs and comparable multiple support. Negative or cyclically distorted EPS may make PE unsuitable |
| EV/EBIT, EV/EBITDA or revenue multiples | Capital-structure comparison or operating metrics that better explain the business | Match EV and metric definitions, leases and shared costs. EBITDA does not fund replacement investment; revenue multiples require a path to margins, cash and funded growth |
| SOTP / segment valuation | Material businesses differ in economics, operating stage or suitable method | Sufficient segment evidence; shared costs/assets, group claims and interdependence. SOTP is a decomposition and can contain other methods, not an independent additional vote |
| DCF / cash-distribution valuation | Cash generation, investment and transition assumptions can be bounded from evidence; may be primary or supporting at any company size | Cash-flow/discount-rate match and the conditional DCF requirements below. Stable mature cash flows can be easier to estimate than early-stage cash flows; investment surges require an evidenced payoff/transition path |
| Milestone / probability-adjusted scenarios | Commercial validation or discrete regulatory/product outcomes dominate | Adoption or success evidence, runway, funding/dilution and failure/recovery outcomes. Probabilities must be justified; otherwise show conditional scenarios without a fabricated expected value |
| Capital / residual-income / asset methods | Regulatory capital, asset realization or restructuring better explains distributable value | Applicable accounting, capital requirements, realizability, costs and claim priority. Use EV/CFO conventions only where operating activity can be meaningfully separated from financing and required capital |

Separate **research emphasis**, **method weights** and **scenario probabilities**. Research emphasis follows material investment questions; it is not a company-quality score that mechanically changes a price-based rating. Default to qualitative primary/supporting roles rather than a numerical blend. If numerical method weights are useful or requested, explain their basis in explanatory power, evidence and shared assumptions; use nonnegative weights summing to 100% on comparable common-equity values at the same target date, currency and share basis. Show each value and the combined result, and sensitize the weights. A reverse valuation is a test of assumptions, not another target to average. Avoid overlap between SOTP components and whole-company values.

Record method roles, any weights and the rating reference before interpreting outputs; revise them for new evidence with a stated reason, not to reach a desired price or letter. Disagreement requires a forecast/definition/capital/method bridge, not automatic averaging. Several models using the same forecast are not independent evidence. A weak supporting model cannot automatically overrule a supported primary method, but material cash, funding or accounting concerns cannot be dismissed by giving them a low weight. If no independent cross-check is available, disclose the limitation and apply V05 rather than manufacture one.

### Parameter evidence and analyst judgment

Use one compact record for decision-material assumptions: observed anchor/source/definition → economic rationale → selected base and credible alternatives → value effect. Label facts, calculations and estimates. M08/M10 own operating inputs; M13 owns valuation inputs.

1. **Choose a representative path.** M08 owns the observed starting point, changes and base operating estimates; use those findings here. Reasoned top-down margins, normalized taxes and valuation multiples are legitimate without unique correctness or an exact bottom-up derivation. Explain economic relevance and contrary evidence, not superiority to every neighboring number. Midpoints or sample medians may represent the business when justified; caution alone does not make a base representative.
2. **Keep definitions and economics consistent.** Reconcile material differences in periods, accounting, business mix and sample selection. Link earnings to cash, investment, funding and claims; consider the payoff horizon and avoid double-counting risks. Historical ROIC, marginal returns, project IRR and WACC are distinct. A calculation that uses an assumed margin and solves a residual cannot independently validate that margin; report the residual’s significance without treating every incomplete cost split as a failed forecast.
3. **Challenge material alternatives proportionately.** Address evidence that could change the business path or valuation. Use sensitivities for reasonable neighboring estimates; apply V05 when only a base band is supportable. Quantify what matters without manufacturing precision or exhaustively testing every plausible combination. Stop when a defensible working judgment and its important alternatives are clear; inability to prove one exact number is not a reason to keep rebuilding.
4. **Explain revisions without targeting a rating.** Follow the independent-record workflow before institutional comparison. Compare external assumptions on compatible definitions; missing original models limit that comparison, not automatically our valuation. Update for facts or a better reasoned interpretation and identify which occurred. Do not tune to an old target, current price, preferred letter or consensus. A supported method can replace a weak tool; it cannot bypass an unresolved material accounting or funding problem.

### Earnings and multiple matching — when using PE

**Inputs:** M08's earnings forecast and F04 adjustment bridge; target date; candidate earnings windows; dated historical, peer and institutional valuation evidence; common-equity/asset boundary.

**Analysis:**
1. Use M08's representative operating path to select the earnings window and PE before interpreting the rating: **target date → EPS period/definition → compatible PE → target value**. For a future PE-based target, prefer earnings over the 12 months following the target date, paired with a multiple calibrated to that forward distance and accounting basis. A nearby full fiscal year may approximate this window; explain material timing differences. Use target-year or cycle-normalized earnings, or another method under V02, when business economics and usable pricing evidence better explain target-date pricing; proximity, easier forecasting or caution alone is insufficient. Specify earnings dates, common-share attribution, diluted shares, currency/share class and equity boundary. For NTM, use quarterly earnings and compatible shares where available; disclose interpolation, seasonality and share-count approximations. A later window does not itself justify retaining the same PE or raising value.
2. Match the evidence to that pair. For historical/peer references identify the pricing date, EPS period and how far forward it looks; a generic "forward PE" label does not establish compatibility. Use forecasts available at that date, not subsequent actual earnings. Apply F04/F08 to material GAAP/IFRS, adjusted and analyst-normalized EPS differences: recurring expenses, SBC, amortization, nonoperating items, tax, preferred/minority claims and dilution; match gross/net revenue and enterprise/equity boundaries too. Classify references as usable calibration after adjustments, broad context or unsuitable, explaining consequential gaps. One observation is not a historical distribution, and broker agreement does not independently establish fair value. Negative or unstable near-zero earnings require a suitable alternative under V02.
3. Use compatible own-history or economically comparable market pricing to anchor PE where available. Explain why growth durability, profitability, cash conversion, reinvestment, competitive position and risk support the selected premium/discount and point within the relevant range. A business-quality label or an unadjusted average is insufficient; a uniquely correct multiple is not required. If a cost or risk already reduces EPS, explain any remaining persistence or uncertainty risk behind a further PE discount. Compare material favorable and neutral/adverse institutional views after the independent judgment: source/date, thesis, target horizon, earnings basis and multiple. Label target/PE as implied EPS only when that target has no other components; unavailable original models limit comparison. Do not average incompatible samples or offset weak earnings with a higher PE to reproduce a desired target.
4. Earnings windows are valuation bases, not operating scenarios: a forward window can value the same base path without requiring bull-case performance first. For decision-material window/definition alternatives, hold that path constant to separate re-expression from changed valuation judgment, then isolate forecast revisions. With positive earnings and an unchanged equity/asset boundary, equivalent PE_new = PE_old × EPS_old / EPS_new. This is a diagnostic, not a requirement to preserve the old target: independently support the selected pair and explain any value change. Keeping the same PE across windows may change value; rolling to another earnings year is not itself a forecast revision. Detailed conversions belong in Workpaper B, not a routine survey of every possible window.
5. Identify whether the multiple prices whole common equity or an explicitly stripped operating business. A quoted share-price/EPS or broker target/EPS ratio normally describes whole equity unless the source shows a separate bridge. Removing investment income from EPS does not by itself strip the corresponding asset value out of that multiple. Add assets or deduct claims separately only with a supported boundary for both earnings and multiple, including related taxes/claims, or use a reconciled SOTP; do not add the same asset to a whole-equity PE value again. Avoid applying EV-to-equity deductions mechanically to an already attributable EPS valuation.

**Outputs:** M13's compact argument for the selected earnings window and PE, resulting target/return, and why this base is more representative than the material alternative; include the current-versus-target comparison and any material basis-change explanation. Keep source adjustments and conversions in Workpaper B, referencing M08/F04. V03/V05 own sensitivity, confidence and rating; the forward-window preference is conditional, with no fixed fiscal year, multiple or rating.

### Value bridges for the selected methods

- **PE:** apply the earnings/multiple matching procedure above; target price = compatible EPS × supported PE, plus only separately justified asset/claim adjustments.
- **EV and SOTP:** bridge to common equity using consistent cash, debt, leases, preferred/convertible and minority claims, other assets and shares. Include corporate costs and intersegment eliminations; group cash/debt is counted once. Restricted/illiquid assets are not automatically available funding; any discount needs evidence or sensitivity.
- **All methods:** align forecasts with M08/M10, cash and financing availability with F07, and target/date/share-class conventions with V01. Show how the observed price relates to the relevant forecast years' earnings or operating metrics, reusing M08 rather than rebuilding the forecast. SBC has a shareholder cost through earnings, dilution or an equivalent claim/cost treatment; avoid omission and duplicate penalties. Repurchases consume cash and affect shares; buyback yield is not an extra return after per-share valuation. Compare market multiples/expectations on matching periods and definitions; explain material differences from identifiable institutional estimates without claiming access to undisclosed models.

### DCF requirements — only when DCF is selected

1. Link operating drivers to revenue, margin, investment and cash consistently with M08/M10. Match FCFF with WACC or FCFE with cost of equity; reconcile from reported CFO/FCF, including interest, cash tax, leases, SBC and working capital. An economic cash-equivalent compensation forecast is not the company's actual bank-cash forecast; maintain funding consistency.
2. Support investment, commissioning, depreciation and asset productivity with available evidence. Separate existing-capacity growth from new capital, payment from asset addition, and growth from replacement spending where supportable. Reconcile shared assets and any R&D capitalization across earnings, assets and reinvestment. Do not infer maintenance capex from depreciation alone or assume unpaid/leased equipment is free.
3. Extend the forecast to a defensible mature state, with justified growth, margins, reinvestment and excess-return duration. A mature reinvestment relation such as g/incremental ROIC requires consistent definitions and evidence for returns, not a generic default. Test economically coherent growth/margin/capital combinations. Early-stage cash flows also need explicit survival, funding/dilution and failure outcomes where material; do not charge the same failure risk twice.
4. Source currency-matched discount-rate components and distinguish observations from beta, ERP, leverage and borrowing-cost choices. For perpetuity models require discount rate above terminal growth, consistent inflation/currency and funded growth. Show final explicit and first terminal year cash flows, inspect the preceding fade period for unsupported releases, and report terminal-value dependence plus economically distant value concentration where material. An exit multiple must not conceal an unsupported mature state.
5. Date cash flows and explain stubs/seasonality. A present DCF value is not automatically a 12-month target: value remaining flows at the target date with corresponding assets, claims and shares, or give a reconciled roll-forward. Exclude elapsed flows and avoid double-counting interim distributions; financing proceeds are not free shareholder value.
6. Test dominant assumptions separately and jointly under V03, including sustained capex and payoff, not merely a narrow WACC/g grid. Distinguish a conditional valuation experiment from evidence supporting a formal target. If long-run inputs cannot support decision-relevant bounds, reduce the tool's role or use another supported method; apply V05 to unresolved problems that still determine the overall conclusion.

**Outputs:** Selected-method roles/evidence and any weight rationale; parameter register; reproducible forecast-to-price/value bridge; dated market comparison and explanation of disagreement. Include DCF transition/terminal tables and operating-to-equity bridges only when applicable. Detailed model tables belong in supporting material; M13 summarizes the decisive assumptions and implications.

## V03 Scenarios, Reverse Valuation, and Robustness

**Inputs:** Selected valuation methods, shared operating forecasts, material parameter evidence, verified price and V05 rating thresholds.

**Analysis:**
1. Distinguish three outputs at the same target date, currency and share basis:
   - **Base price:** the value of V02's representative central path, used for the main return judgment. When evidence supports only a base band, identify that exception and use V05; the band is not a substitute for choosing a supportable main judgment.
   - **Bear lower bound–bull upper bound:** the endpoints of the covered, evidence-grounded adverse and favorable scenarios. Derive each from coherent demand, pricing, margins, investment, collection, financing and dilution. Explain what makes each endpoint credible and what must happen to reach it. Do not combine independent parameter extremes that cannot coexist, add unsupported upside, or charge a risk twice. These are conditional scenario bounds, not statistical confidence limits or absolute trading limits; M15 owns material losses outside the covered scenarios.
   - **Sensitivity interval:** values from varying identified inputs over justified ranges while stating what stays fixed and any necessary linked adjustments. It diagnoses model dependence; it is not another scenario range or base valuation band by default.
   Show scenario earnings/cash metrics, valuation assumptions, prices, price changes, distributions and total returns. If an endpoint cannot be supported after proportionate evidence gathering, mark it unquantified with the missing determinant; never invent a number to fill the conclusion. Use each output's label consistently in M01/M13/M17.
2. Test what the price requires using a method suited to the question: implied EPS, growth, margin, share, cash generation or investment efficiency. For PE, today's conditional EPS is P0/multiple; target-date EPS required for total return r is (P0×(1+r)−D)/target multiple. At r=0 this includes dividends and differs from a price-only match. Explain fixed assumptions, period, feasible range and operating implications; a current PE quotation alone is not reverse valuation. Implied assumptions are conditional, not uniquely observed market beliefs.
3. If reverse DCF is used, solve through the same asset/claim and timing bridge; state the solved variable, fixed assumptions, feasible bounds and equation/residual. Test an alternative economically distinct combination when the ambiguity matters. Match today's price separately from a target-date required return. A failed solve within chosen bounds is not proof that no feasible business path can support the price.
4. Sensitize the dominant operating and valuation drivers, with one-factor attribution and coherent joint cases when material. Define defensible ranges before using results to choose a preferred conclusion. Where a threshold affects action, show the approximate change needed to cross it. Use the result to describe conviction and reassessment conditions under V05, not to select parameters or demand invariant ratings. A focused set of material tests is sufficient; neither a narrow grid nor an exhaustive one proves the forecast.
5. Scenario probabilities may be reasoned analyst judgments, labeled as such; explain the relative likelihoods, use nonnegative weights totaling 100%, and test material weighting effects. Otherwise show unweighted scenarios. Keep scenario probabilities separate from V02 method weights and do not multiply independently chosen weights across inconsistent business cases. Grid counts, subjective simulations or agreement among correlated methods are not calibrated success probabilities.
6. For report updates, freeze the old result and separate price/time refresh, new facts, forecast revisions, parameter selection and method/asset-boundary changes. Use matched-input tests to explain disputed drivers and identify interactions/order for joint changes. Newly introduced long-run assumptions are not a purely mechanical method change; changed ratings need not reflect changed company fundamentals.

**Outputs:** Bear lower bound, base price/band and bull upper bound with coherent drivers and returns; separately labeled sensitivity intervals, conditional price-implied requirements, rating-critical conditions and their evidence, and an old-to-new bridge for updates. Reverse DCF is optional; a reproducible expectations test is required.

## V04 Return Calculation and Attribution

For scenario s, target-date price Ps and expected per-share dividends Ds:

- Total return Rs=(Ps+Ds-P0)/P0.
- Weighted return Rw=Σws×Rs and weighted price Pw=Σws×Ps; also weight differing dividends.
- Default preliminary rating uses **base-case total return Rbase** from the selected primary method, or the predeclared V02 method blend within the base operating scenario. Method weights and scenario probabilities are distinct. Do not switch opportunistically to the larger method result or probability-weighted scenario return. For a base valuation band, calculate the return bounds from the compatible underlying paths, including their distributions; do not use an arbitrary midpoint or combine incompatible price/dividend extremes. Apply V05 to those returns without turning their rating span into a recommendation. A different explicitly requested reference must be selected before calculation.
- Under a PE decomposition, price return=(EPS_H/EPS_ref)×(PE_H/PE_ref)-1, with PE_ref=P0/EPS_ref. Define periods and snapshots. If current and target valuations use the same forward EPS, the difference is multiple change; a forecast revision needs separately defined old/new estimates.
- For horizons other than 12 months disclose whole-period return and the annualization convention. If no better explicit rule is selected, convert annual thresholds by compounding to H and disclose the assumption. Treating interim dividends as received at the end is an approximation that must be stated.

**Outputs:** Base/scenario returns, capital appreciation versus dividends, earnings/valuation drivers, and time/FX sensitivities.

## V05 Preliminary and Final Rating

Use these internal 12-month return conventions unless the user specifies another policy. Do not assume they match the rating definitions of another report. Map unrounded base returns consistently; a small threshold crossing changes the label, not necessarily the economic assessment or conviction:

| Preliminary rating | Meaning | Base total return |
|---|---|---|
| A | Strong Buy | R ≥ 25% |
| B+ | Buy | 15% ≤ R < 25% |
| B | Positive / Selective Accumulation | 5% ≤ R < 15% |
| C | Hold / Watch | -10% ≤ R < 5% |
| D | Reduce / Avoid | R < -10% |
| NR | Not Rated | Critical evidence or valuation path is insufficient |

**Inputs:** Base return, confidence in the business/valuation path, downside and funding exposure, material sensitivities and verification timing.

**Analysis:**
1. Present one main judgment: whether the business outlook and prospective return make the observed price attractive. State the return-based letter, meaning and conviction separately. Explain whether the return compensates for downside and execution risk; no universal upside/downside ratio is required.
2. Retain a defensible representative base when reasonable estimates cross a rating boundary. Show the relevant alternative and its practical effect: modest attraction, stronger opportunity or limited conviction. A crossing alone does not invalidate the forecast, require NR or justify an automatic downgrade. Conversely, a mechanical letter does not establish a strong buy case. Do not tune assumptions to preserve a letter.
3. Correct factual, calculation and material definition errors before rating. Reflect material risks in earnings, cash, funding, shares or valuation; do not charge them again through an unexplained rating penalty. Identify any explicit policy override. Company quality alone cannot raise a return-based letter.
4. If only a base band is justified, show it and assess whether a representative judgment is still possible using V02. Do not invent a midpoint to obtain a letter. Use **NR only when a material unresolved fact, accounting inconsistency, funding constraint or lack of a credible valuation basis prevents a defensible judgment after proportionate investigation**. Examples include unreliable earnings or a dominant valuation input with no usable evidence anchor. Document the actual blocker and what would resolve it; suspend formal targets and entry recommendations, while retaining conditional analysis. Ordinary forecast judgment, unavailable product detail or broker models, a weak unused tool, and reasonable scenarios spanning ratings are not sufficient reasons for NR.
5. For updates, distinguish changed business evidence from revised estimates, price movement and threshold effects. A lower price requires checking intervening facts before changing the recommendation.

**Outputs:** One main letter or NR, plain-language investment judgment, return/horizon, conviction, downside compensation and reassessment conditions. Put the decisive reasoning here once; M01/M17 summarize it.

## V06 Entry Prices and Dynamic Rating Bands

**Inputs:** Supported base target or compatible base-band paths, associated dividends, and required return r.

**Analysis:**
1. For each supported base path, entry-price ceiling Pmax=(Pbase+Dbase)/(1+r), for r>-100%. A base band produces a threshold interval: the lowest ceiling meets the arithmetic return requirement across the covered base paths; the highest meets it only under the favorable base calibration. Label these meanings. Do not silently use a midpoint.
2. First obtain the effective whole-horizon thresholds from V04 and any explicit user rating policy. With the default annual thresholds and a horizon of H years, use r_H=(1+r_annual)^H-1. Compute each band's price boundary for each supported base path from those effective thresholds. For the default 12-month horizon only, denote the boundaries P25/P15/P5/P-10: 0<P0≤P25 is A's return band; P25<P0≤P15 is B+; P15<P0≤P5 is B; P5<P0≤P-10 is C; above P-10 is D. Do not reuse these fixed percentage labels or prices for a different horizon or custom policy.
3. These are **arithmetic return bands**, not automatic recommendations. Carry any V05 risk restriction into the price table; a lower price alone does not remove it.
4. Revalue before recomputing thresholds when earnings, financing, distributions, FX, or valuation assumptions change. Roll dates and the forecast basis when the horizon advances.

**Outputs:** Threshold prices, current-price band, applicable risk limitations, and model-validity conditions. Do not imply guaranteed returns or automatic trade instructions.

**Arithmetic example:** A 12-month target of 120 plus 2 dividends gives thresholds 97.60/106.09/116.19/135.56. Price 100 implies 22%, preliminary B+; price 120 implies about 1.67%, preliminary C. This fictional example has no final risk rating.

**Horizon consistency example:** Over 24 months, the default 15% annual Buy threshold becomes 32.25% total return, and the 5% annual Positive threshold becomes 10.25%. A target of 120 plus 2 total dividends at price 100 implies 22% over two years, so the preliminary band is B, not B+. Its Buy entry ceiling is 122/1.3225=92.25. The same effective thresholds must classify returns and generate the price table.

## V07 Cross-Currency, Cross-Listing, and ADR Treatment

**Inputs:** Actual FX and direction, depositary/share ratio, synchronized or clearly timed quotes, rights, and premiums/discounts.

**Analysis:** If one ADR represents n local shares and FX is local-currency units per dollar, theoretical ADR price without premium=local price×n/FX. Verify units and ratio. A market price ratio may include premium and asynchronous trading; it is not spot FX. State target FX and premium assumptions and convert dividends consistently. Do not mechanically equate securities with differing rights.

**Outputs:** Actual quote, theoretical conversion, premium, and forecast assumptions separately; distinguish underlying price effects from FX effects.
