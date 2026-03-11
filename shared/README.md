# Phase 1 — Shared Preprocessing

## About This Directory

This folder contains all collaborative preprocessing work done jointly by the entire group before individual model development begins. The work is divided into **4 parallel preprocessing notebooks** (Teams 1–4), each responsible for a distinct subset of columns, and **1 final merge notebook** (Team 5) that combines all outputs into the cleaned, standardized dataset.

---

## Dataset

The raw dataset contains car listing data scraped from **arabam.com**, originally containing **3424 rows** and **53 columns**.

Before any team began preprocessing, the **group leader** performed an initial cleanup pass directly on the raw data, producing `raw_dataset.csv` which all teams read from. The following columns were removed at this stage:

| Column | Reason for Removal |
|---|---|
| `Şanzıman` | ~63% missing values |
| `Ağır Hasarlı` | ~53% missing values plus ~11% "Belirtilmemiş" entries → over 64% unreliable |
| `Yakıt Tüketimi` | Redundant aggregate column; its information is already split into `Ortalama Yakıt Tüketimi`, `Şehir İçi Yakıt Tüketimi`, and `Şehir Dışı Yakıt Tüketimi` |
| `Motor ve Performans` | Redundant for the same reason; data already available in dedicated columns |
| `Boyut ve Kapasite` | Removed after extracting the only non-redundant value it contained (`Aks Aralığı`) into a new dedicated column |
| `Plaka Uyruğu` | Near-zero variance: ~99.4% of values were Turkish, with only 3 exceptions |
| `Kopyalandı` | ~72% unique values, indicating it functions as a near-identifier with no learnable pattern |
| `_URL` | Unique identifier per record (~72% unique values) |
| `_Başlık` | Same reason as `_URL` |

---

## Notebook Pipeline

Teams 1–4 are **parallel** (all read from the same `raw_dataset.csv`). Team 5 runs **last** and merges all outputs.

| Notebook | Team | Input | Output | Task Summary |
|---|---|---|---|---|
| `01_core_numeric.ipynb` | Team 1 | `raw_dataset.csv` | `df_team1` | Clean and convert core numeric & date columns (`Fiyat`, `Yıl`, `Kilometre`, `İlan Tarihi`) |
| `02_categorical_encoding.ipynb` | Team 2 | `raw_dataset.csv` | `df_team2` | Encode all categorical columns describing car classification, type, and seller info |
| `03_paint_damage.ipynb` | Team 3 | `raw_dataset.csv` | `df_team3` | Engineer numeric features from free-text paint & body damage columns |
| `04_technical_specs.ipynb` | Team 4 | `raw_dataset.csv` | `df_team4` | Strip units and clean all technical specification & insurance columns |
| `05_final_merge.ipynb` | Team 5 | `df_team1`–`df_team4` | `processed_dataset.csv` | Merge all outputs, remove duplicates, cap outliers, apply StandardScaler |

---

## How to Run

All notebooks are designed for **Google Colab**. Each notebook reads `raw_dataset.csv` directly from the GitHub raw URL — no local files are needed.

**No setup is required** beyond opening the notebook in Colab and running all cells.

- Notebooks `01`–`04` can be run in **any order** (or simultaneously), as they are fully independent.
- Notebook `05` must be run **after** all four team notebooks have been verified. Paste the code from each team notebook into the designated banner sections in `05_final_merge.ipynb`.
- The final output `processed_dataset.csv` is produced by notebook `05` and should be committed to `data/processed_dataset.csv`.

---

## Column Ownership

| Notebook | Columns |
|---|---|
| `01_core_numeric.ipynb` | `Fiyat`, `Yıl`, `Kilometre`, `İlan Tarihi` |
| `02_categorical_encoding.ipynb` | `Marka`, `Seri`, `Model`, `Vites Tipi`, `Yakıt Tipi`, `Kasa Tipi`, `Renk`, `Çekiş`, `Kimden`, `Sınıfı` |
| `03_paint_damage.ipynb` | `Boya-değişen`, `Orjinal`, `Lokal boyalı`, `Boyalı`, `Değişmiş`, `Belirtilmemiş` → engineered as `total_painted_parts`, `total_changed_parts`, `is_fully_original`, `paint_damage_score`, `Boya-değişen_count` |
| `04_technical_specs.ipynb` | `Motor Hacmi`, `Motor Gücü`, `Ort. Yakıt Tüketimi`, `Yakıt Deposu`, `Üretim Yılı (İlk/Son)`, `Ortalama Kasko`, `Ortalama Trafik Sigortası`, `Silindir Sayısı`, `Tork`, `Maksimum Güç`, `Minimum Güç`, `Hızlanma (0-100)`, `Maksimum Hız`, `Ortalama Yakıt Tüketimi`, `Şehir İçi Yakıt Tüketimi`, `Şehir Dışı Yakıt Tüketimi`, `Uzunluk`, `Genişlik`, `Yükseklik`, `Ağırlık`, `Boş Ağırlığı`, `Koltuk Sayısı`, `Bagaj Hacmi`, `Ön Lastik` → `Jant Boyutu`, `Aks Aralığı` |
