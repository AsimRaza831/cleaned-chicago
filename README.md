# Chicago Census Data Cleaning

Cleaning and structuring of the Chicago community area socioeconomic indicators
dataset (78 rows: housing crowding, poverty, unemployment, education, income,
and hardship index by community area).

## Issues found in the raw data (`messy_chicago_census.xlsx`)

- **Inconsistent capitalization** — e.g. `Humboldt park` instead of `Humboldt Park`
- **A citywide summary row mixed in with individual community areas** — the last
  row (`CHICAGO`) is a city-wide average, not a community area, and was sitting
  in the same table as the 77 actual areas
- **Wrong data types** — `COMMUNITY_AREA_NUMBER` and `HARDSHIP_INDEX` were stored
  as decimals (e.g. `1.0`) instead of whole numbers
- **Missing values** in the summary row for fields that don't apply to it
  (area number, hardship index)

## What I did

1. Standardized text casing across `COMMUNITY_AREA_NAME`
2. Separated the citywide summary row from the 77 community-area rows into its
   own sheet, so area-level analysis isn't skewed by a city-wide average
3. Converted ID and index columns to proper integers
4. Sorted community areas by area number and formatted the sheet for readability
   (bold headers, frozen header row, auto-sized columns)

## Files

| File | Description |
|---|---|
| `messy_chicago_census.xlsx` | Original raw data, as received |
| `cleaned_chicago_census.xlsx` | Cleaned data — `Community Areas` sheet (77 rows) + `Citywide Summary` sheet (1 row) |

## Result

78 mixed rows → 77 clean, consistently formatted community-area records +
1 correctly separated citywide summary, ready for pivot tables or mapping by
community area.

---
*For custom Excel data cleaning work, see my
[Fiverr gig](https://www.fiverr.com/s/L3deQVa).*
