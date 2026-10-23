# Senior software developer monthly cost by country

What a company pays per month for one senior software developer, all in, by country.
Seven rows, ordered by price. Published as CSV and JSON under CC BY 4.0.

| Country | Senior, per month (USD) | Overlap with U.S. hours |
|---|---|---|
| Philippines | $2,000–4,000 | None without a night shift |
| India | $2,500–4,500 | None without a night shift |
| Argentina | $4,000–6,500 | 7–8 hours |
| Brazil * | $4,000–6,500 | 7–8 hours with U.S. Eastern, 4–5 with Pacific |
| Mexico | $4,500–7,000 | 7–8 hours on a normal schedule |
| Poland | $6,000–9,000 | 2–3 hours, at the edge of the Polish day |
| A U.S. remote hire | $13,000–17,000 | Full |

\* The country the publisher sells engineers from. Read the whole thing knowing that.

## Who published this, and the bias you should assume

HireBrazilDevs, a studio that places Brazilian engineers with North American
companies. We have an interest in Brazil looking good, so the first thing worth
pointing out is that **the Philippines and India cost less than Brazil** and the
table says so in the first rows. A cost table where the publisher comes out
cheapest is worth nothing to the person reading it.

What the price buys at each step — and where the cheaper option is the right
one — is written out at
<https://hirebrazildevs.com/developer-rates-by-country>.

## Method

Each range is the figure published on the corresponding country comparison page
on hirebrazildevs.com, kept in one place so no two pages can disagree. The
`source_url` column points at the page for that row.

These are ranges, not quotes: a scarce stack sits near the top of a range and a
generalist near the bottom. The U.S. row is a **fully loaded employee** — salary
plus payroll tax, benefits and insurance — not a contractor rate, which is why
it is not comparable to the others line for line without saying so.

Figures are in U.S. dollars, per engineer, per month, as a company pays them.
Not take-home pay.

## Files

- `developer-rates-by-country.csv` — 7 rows, header included
- `developer-rates-by-country.json` — same data, with the method and caveats inline

Both are also served live, with CORS open, at:

- <https://hirebrazildevs.com/data/developer-rates-by-country.json>
- <https://hirebrazildevs.com/data/developer-rates-by-country.csv>

## Licence

[CC BY 4.0](https://creativecommons.org/licenses/by/4.0/). Use it in a post, a
deck, a spreadsheet or a model. The only condition is attribution.

Suggested citation:

> "Senior developer monthly cost by country", HireBrazilDevs, 2026.
> https://hirebrazildevs.com/developer-rates-by-country

## Updating

Generated, never edited by hand:

```
node scripts/build-data-package.mjs
```

The source of the numbers is `site/src/domain/hire-countries.js`, which derives
them from the comparison pages. A test fails if the files on disk stop matching
what the source produces — the first version of this package was a copy, and a
copy of a number is a number that goes stale in silence.
