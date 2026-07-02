# DXY 1m OHLCV Forex Historical Data — Free Sample

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE) [![Dataset rows](https://img.shields.io/badge/full_dataset-4_713_327_rows-blue)](https://ork.ad/) [![Updated](https://img.shields.io/badge/weekly_update-every_Sunday-green)]() [![Full data on ork.ad](https://img.shields.io/badge/download-ork.ad-orange)](https://ork.ad/)

### → [**Download the full DXY dataset on ork.ad**](https://ork.ad/)

**DXY 1m OHLCV Forex historical data** — ultra high-quality one-minute OHLCV for **US Dollar Index**. 24/5 FX liquidity with Asian, European and US sessions — not limited to US market hours. Clean `time, open, high, low, close, volume` CSV for backtesting, algorithmic trading and quantitative research.

## Table of contents

- [Why this dataset?](#why-this-dataset)
- [Download sample CSV](#download-sample)
- [GitHub Pages preview](#github-pages)
- [Sample vs full dataset](#sample-vs-full-dataset)
- [Timeframes on ork.ad](#timeframes-on-orkad)
- [Weekly updates](#weekly-updates)
- [Data preview](#data-preview)
- [Schema](#schema)
- [Code examples](#code-examples)
- [Download full data on ork.ad](#download-full-data)

## Why this dataset?

- **Ultra high-quality 1-minute OHLCV** for **US Dollar Index** (Forex)
- **24/5 FX liquidity with Asian, European and US sessions — not limited to US market hours**
- **Clean CSV schema** — `time, open, high, low, close, volume` (no gaps in formatting)
- **Free evaluation sample** on GitHub (`1m` only) · **13 timeframes** on [ork.ad](https://ork.ad/) · **4,713,327** `1m` rows in the full archive
- Built for **backtesting**, **algorithmic trading** and **quantitative finance** workflows
- **Weekly refresh** — [ork.ad](https://ork.ad/) every **Sunday**; GitHub `1m` sample updated in sync

> **Sample on GitHub** · `DXY_1m.csv` (172,228 rows, `2025-12-02` → `2026-06-02`). **Full archive on [ork.ad](https://ork.ad/)** — **4,713,327** `1m` rows (~240.32 MB), **13 timeframes** (``1m`, `3m`, `5m`, `15m`, `30m`, `1H`, `2H`, `4H`, `8H`, `12H`, `16H`, `1D`, `1W``), `2012-10-07` → `2026-06-02`.

## Download sample

**[DXY_1m.csv](https://github.com/ork-ad/dxy-1m-ohlcv-forex-historical-data/blob/main/DXY_1m.csv)** on GitHub ([raw CSV](https://raw.githubusercontent.com/ork-ad/dxy-1m-ohlcv-forex-historical-data/main/DXY_1m.csv)) · [GitHub Releases](https://github.com/ork-ad/dxy-1m-ohlcv-forex-historical-data/releases) when the release workflow is active.

## GitHub Pages

Interactive chart & stats: **[https://ork-ad.github.io/dxy-1m-ohlcv-forex-historical-data/](https://ork-ad.github.io/dxy-1m-ohlcv-forex-historical-data/)**

## Sample vs full dataset

| | **Sample (this repo)** | **Full dataset ([ork.ad](https://ork.ad/))** |
|---|--:|---|
| Instrument | US Dollar Index · Forex | US Dollar Index · Forex |
| Timeframes | `1m` only (sample) | **13** — `1m`, `3m`, `5m`, `15m`, `30m`, `1H`, `2H`, `4H`, `8H`, `12H`, `16H`, `1D`, `1W` |
| 1m rows | 172,228 | **4,713,327** |
| Size | 8.01 MB | ~240.32 MB |
| Period | `2025-12-02` → `2026-06-02` | `2012-10-07` → `2026-06-02` |
| File | `DXY_1m.csv` | ZIP on [ork.ad](https://ork.ad/) |
| Updates | Weekly (Sunday) — GitHub sample | Weekly (Sunday) — all timeframes |

## Timeframes on ork.ad

This GitHub repository ships a **1-minute (`1m`) evaluation sample** only. On **[ork.ad](https://ork.ad/)**, each full asset archive is delivered as a ZIP with **13 gap-free OHLCV timeframes** (one CSV per timeframe):

**1m** · **3m** · **5m** · **15m** · **30m** · **1H** · **2H** · **4H** · **8H** · **12H** · **16H** · **1D** · **1W**

GitHub = `1m` sample · [ork.ad](https://ork.ad/) = all **13** timeframes above for the same instrument.

## Weekly updates

- **[ork.ad](https://ork.ad/)** — Full datasets on ork.ad are updated every Sunday.
- **GitHub (this repo)** — GitHub 1m samples are refreshed weekly (every Sunday), in sync with ork.ad.

When a new `1m` sample is published on GitHub, the README, chart preview and CSV reflect the latest week of data.

## Data preview

First and latest rows from the GitHub sample **`DXY_1m.csv`**:

**First rows**

| time | open | high | low | close |
| --- | --- | --- | --- | --- |
| 2025-12-02T10:09:00Z | 99.487 | 99.493 | 99.485 | 99.487 |
| 2025-12-02T10:10:00Z | 99.486 | 99.488 | 99.485 | 99.487 |
| 2025-12-02T10:11:00Z | 99.489 | 99.504 | 99.489 | 99.502 |
| 2025-12-02T10:12:00Z | 99.504 | 99.51 | 99.497 | 99.508 |
| 2025-12-02T10:13:00Z | 99.506 | 99.513 | 99.494 | 99.497 |

**Last rows**

| time | open | high | low | close |
| --- | --- | --- | --- | --- |
| time | open | high | low | close |
| 2026-06-02T10:05:00Z | 99.141 | 99.141 | 99.115 | 99.115 |
| 2026-06-02T10:06:00Z | 99.113 | 99.122 | 99.112 | 99.122 |
| 2026-06-02T10:07:00Z | 99.121 | 99.127 | 99.12 | 99.122 |
| 2026-06-02T10:08:00Z | 99.124 | 99.124 | 99.118 | 99.123 |

## Schema

```text
time,open,high,low,close
```

## Code examples

### pandas

```python
import pandas as pd

df = pd.read_csv('DXY_1m.csv', parse_dates=['time'])
df.set_index('time', inplace=True)
print(df.describe())
print(df.resample('1h').agg({'open': 'first', 'high': 'max',
                              'low': 'min', 'close': 'last', 'volume': 'sum'}).head())
```

### backtrader

```python
import backtrader as bt
import pandas as pd

df = pd.read_csv('DXY_1m.csv', parse_dates=['time'])
df.set_index('time', inplace=True)

class PandasData(bt.feeds.PandasData):
    params = (('datetime', None), ('open', 'open'), ('high', 'high'),
              ('low', 'low'), ('close', 'close'), ('volume', 'volume'))

cerebro = bt.Cerebro()
cerebro.adddata(PandasData(dataname=df))
# cerebro.addstrategy(YourStrategy)
# cerebro.run()
```

### vectorbt

```python
import pandas as pd
import vectorbt as vbt

df = pd.read_csv('DXY_1m.csv', parse_dates=['time'])
close = df.set_index('time')['close']
fast, slow = vbt.MA.run(close, 10), vbt.MA.run(close, 50)
entries = fast.ma_crossed_above(slow)
exits = fast.ma_crossed_below(slow)
pf = vbt.Portfolio.from_signals(close, entries, exits, init_cash=10_000, freq='1min')
print(pf.stats())
```

## Download full data

The complete **DXY** archive on **[ork.ad](https://ork.ad/)** includes **13 OHLCV timeframes** (`1m`, `3m`, `5m`, `15m`, `30m`, `1H`, `2H`, `4H`, `8H`, `12H`, `16H`, `1D`, `1W`) — **4,713,327** rows at `1m`, plus all higher timeframes in the same ZIP.

**[→ Get the full DXY dataset on ork.ad](https://ork.ad/)**

---
*GetData · DXY 1m OHLCV sample on GitHub · Full historical data on [ork.ad](https://ork.ad/) · 2026-07-02 UTC*