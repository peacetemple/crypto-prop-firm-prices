# Crypto prop firm challenge prices and terms

[![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.24053046.svg)](https://doi.org/10.5281/zenodo.24053046)

**Live, browsable version:** <https://cryptopropfirms.com/prices/>  
**Payout complaint study:** <https://cryptopropfirms.com/complaints/>  
**Support study:** <https://cryptopropfirms.com/support/>  
**Machine-readable entry point:** <https://cryptopropfirms.com/llms.txt>

A dated dataset of what crypto proprietary-trading ("prop") firms publish about their own challenges. 386 rows,
21 firms, one CSV plus the same records as JSON with per-firm sources.

A dated dataset of what crypto proprietary-trading ("prop") firms publish about their own challenges: the price of
every account size and format, the profit split, the drawdown rule in the firm's own wording, the profit target, when
identity verification is triggered, how a payout is sent, and the page each figure was read from.

## What makes it different from a comparison article

Every row carries `source_url` — the page on the firm's own site the figure was read from — and the whole file is
regenerated from that record, so a number cannot drift away from its source. Where a firm publishes nothing for a
field the cell says so; nothing is estimated, averaged or carried over from another plan. Promotional prices are
included only where the firm's own checkout shows them, and the standing list price is printed beside them in
`list_fee_usd`.

## Files

| File | What it is |
|---|---|
| `crypto-prop-firm-prices.csv` | one row per firm × account size × format (≈380 rows), the primary table |
| `facts.json` | the same record in JSON, plus per-firm metadata, sources, rule blocks and regulator checks |
| `README.md` | this file: method, columns, provenance and licence |

## Columns (CSV)

- `firm` — the firm's trading name
- `account_size_usd` — the account size the price buys, in US dollars
- `format` — the product or plan name exactly as the firm writes it
- `fee_usd` — the price the firm's checkout charges for that row
- `list_fee_usd` — the standing price before any promotion or code, where the firm publishes one
- `profit_split` — the split as the firm words it, including any paid upgrade path
- `drawdown` — the maximum loss rule verbatim, which is static at some firms, trailing at others and plan-dependent at most
- `profit_target` — the pass mark the firm states for that same row
- `kyc` — when identity verification is triggered: before activation, before payout, or none published
- `payout_rail` — how the payout is sent (which network, chain or bank rail)
- `payout_speed` — the firm's own wording for how long a payout takes
- `source_url` — the page the row's figures were read from
- `regulator_notice` — any warning-list entry found for that firm, with the authority and the date
- `discount_code` — a code the firm publishes, where one applies

## Method, and its limits

Each firm's own pricing, rules and FAQ pages are read by hand and recorded with the date. A firm enters the dataset
only if it sells crypto challenges; firms that are not crypto-first are excluded rather than mixed in.

Three limits worth stating plainly:

1. **This is what firms publish, not what traders experience.** A stated payout time is a marketing claim; the dataset
   records it as a claim, with the firm's wording, not as a measurement.
2. **Coverage is partial by design.** Sizes a firm does not publish are absent rather than estimated, and a field a
   firm leaves silent is marked "Not published" rather than filled with a competitor's number.
3. **It is a snapshot.** Terms change; the `source_url` and the site's own change log are how a reader checks whether a
   row is still true.

## Licence and citation

Released under **CC BY 4.0**: use it, quote it, republish it, including commercially, with attribution.

> CryptoPropfirms.com, "Crypto prop firm challenge prices and terms", <https://cryptopropfirms.com/prices/>, accessed
> YYYY-MM-DD.

Corrections are welcome and are the point of the exercise: if a figure is wrong, the source page is in the row.
