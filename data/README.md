# ETH Gas Data Sources

This directory contains ETH gas-price time series and lightweight preprocessing utilities.

## Dataset

### `ETH_GAS.csv`

Expected columns (adapt as necessary for your data source):

- `Date` (`YYYY-MM-DD`)
- `Open` (optional)
- `High` (optional)
- `Low` (optional)
- `Close` (price / gas metric)
- `Volume` (optional)

The code treats this file as a chronological time series; missing fields are tolerated.

## Utilities

- `preview_data.py` — quick profile of date range, return statistics, and volatility.
- `build_eth_feature_snapshot.py` — computes rolling indicators and exports JSON snapshot.

## Usage

```bash
python3 data/preview_data.py
python3 data/build_eth_feature_snapshot.py
```

## Notes

- Keep rows sorted by `Date` ascending.
- Remove commas from numeric fields if present.
- Missing rows (e.g., gaps) are fine.
