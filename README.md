# India-Stocks-1621-1650-Historical-Data

Institutional Historical 1-Minute Market Data Archive for **India Equities (Constituents 1621 to 1650)** with automated daily cloud capture via GitHub Actions.

---

## 🏛️ Directory Hierarchy

```text
India-Stocks-1621-1650-Historical-Data/
├── .github/workflows/daily_ingest.yml
├── fetch_batch.py
├── README.md
├── <SYMBOL>/
│   └── 1m/
│       ├── README.md
│       └── <YYYY>/
│           └── <MM>/
│               ├── <SYMBOL>_1m_<YYYY-MM-DD>.csv
```

---

## ⏰ 4-Tier Automated Schedule (Mon–Fri)

| Trigger | Time (IST) | Cron (UTC) | Role |
|:---|:---:|:---:|:---|
| **Primary Trigger** | **15:45 IST** | `15 10 * * 1-5` | 15 mins post-market close |
| **Backup Trigger 1** | **16:45 IST** | `15 11 * * 1-5` | 1 hour safety net |
| **Backup Trigger 2** | **17:45 IST** | `15 12 * * 1-5` | 2 hours safety net |
| **Backup Trigger 3** | **18:45 IST** | `15 13 * * 1-5` | 3 hours safety net |

---

## 📦 Constituents (1621 to 1650)

| # | Symbol | Company Name | Yahoo Ticker |
|---|---|---|---|
| 1621 | `MATRIMONY` | Matrimony.Com Limited | `MATRIMONY.NS` |
| 1622 | `MAWANASUG` | Mawana Sugars Limited | `MAWANASUG.NS` |
| 1623 | `MAXESTATES` | Max Estates Limited | `MAXESTATES.NS` |
| 1624 | `MAXIND` | Max India Limited | `MAXIND.NS` |
| 1625 | `MAYURUNIQ` | Mayur Uniquoters Ltd | `MAYURUNIQ.NS` |
| 1626 | `MAZDA` | Mazda Limited | `MAZDA.NS` |
| 1627 | `MBAPL` | Madhya Bharat Agro Products Limited | `MBAPL.NS` |
| 1628 | `MBECL` | Mcnally Bharat Engineering Company Limited | `MBECL.NS` |
| 1629 | `MBEL` | M & B Engineering Limited | `MBEL.NS` |
| 1630 | `MBLINFRA` | MBL Infrastructure Limited | `MBLINFRA.NS` |
| 1631 | `MCCHRLS-B` | Mac Charles India Limited | `MCCHRLS-B.NS` |
| 1632 | `MCL` | M TEK COPPER LIMITED | `MCL.NS` |
| 1633 | `MCLEODRUSS` | Mcleod Russel India Limited | `MCLEODRUSS.NS` |
| 1634 | `MCLOUD` | Magellanic Cloud Limited | `MCLOUD.NS` |
| 1635 | `MEDIASSIST` | Medi Assist Healthcare Services Limited | `MEDIASSIST.NS` |
| 1636 | `MEDICAMEQ` | Medicamen Biotech Limited | `MEDICAMEQ.NS` |
| 1637 | `MEDICAPQ` | Medi Caps Limited | `MEDICAPQ.NS` |
| 1638 | `MEDICO` | Medico Remedies Limited | `MEDICO.NS` |
| 1639 | `MEDPLUS` | Medplus Health Services Limited | `MEDPLUS.NS` |
| 1640 | `MEGASTAR` | Megastar Foods Limited | `MEGASTAR.NS` |
| 1641 | `MEIL` | Mangal Electrical Industries Limited | `MEIL.NS` |
| 1642 | `MENNPIS` | Menon Pistons Limited | `MENNPIS.NS` |
| 1643 | `MENONBE` | Menon Bearings Limited | `MENONBE.NS` |
| 1644 | `MEP` | MEP Infrastructure Developers Limited | `MEP.NS` |
| 1645 | `MERCANTILE` | Mercantile Ventures Limited | `MERCANTILE.NS` |
| 1646 | `MERCURYEV` | Mercury Ev-Tech Limited | `MERCURYEV.NS` |
| 1647 | `METROBRAND` | Metro Brands Limited | `METROBRAND.NS` |
| 1648 | `METROGLOBL` | Metroglobal Limited | `METROGLOBL.NS` |
| 1649 | `METROPOLIS` | Metropolis Healthcare Limited | `METROPOLIS.NS` |
| 1650 | `MFML` | Mahalaxmi Fabric Mills Limited | `MFML.NS` |


---

## ⚡ 1-Line Pandas Stream Loader

```python
import pandas as pd

# Example: Stream MATRIMONY 1m data
url = "https://raw.githubusercontent.com/parshant65-lang/India-Stocks-1621-1650-Historical-Data/main/MATRIMONY/1m/2026/10/MATRIMONY_1m_2026-10-12.csv"
df = pd.read_csv(url)
print(df.head())
```
