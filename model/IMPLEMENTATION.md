# Tesla Forecast Model - Implementation Summary

## Model Overview

- **Input data**: monthly TSLA OHLCV from `data/TSLA_Stock_Dataset_2012_2026.csv`
- **Core signal**: historical average return + return volatility
- **Output**: predicted next close, expected return %, bullish probability

## Files

```
model/
├── tsla_nn.c
├── Makefile
├── evaluate.py
├── demo.sh
├── quickstart.sh
└── README.md
```

## Forecast Logic

1. Parse close prices chronologically.
2. Compute returns across history.
3. Store aggregate statistics in `tsla_model.bin`.
4. Predict next close from latest close and expected return.
5. Estimate bullish probability from expected return vs volatility.

## Commands

```bash
make train
make predict
make eval
```

## Next Enhancements

- Add rolling-window retraining by forecast date
- Add technical indicators (RSI, MACD, ATR)
- Add benchmark comparison against naive random-walk model

## 📚 Files for Reference

- [model/README.md](model/README.md) - Forecast workflow docs
- [model/tsla_nn.c](model/tsla_nn.c) - C99 forecast source
- [model/Makefile](model/Makefile) - Build/run targets
- [model/evaluate.py](model/evaluate.py) - Directional evaluation
- [data/README.md](data/README.md) - Dataset documentation

---

**Result**: A Tesla-specific forecasting baseline in C99 with reproducible build, evaluation, and table generation workflows.
