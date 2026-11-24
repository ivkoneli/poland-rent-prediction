# Predviđanje vremena rešavanja prijava pacova u Njujorku

Projekat iz predmeta veštačka inteligencija (I projekat).

## Problem

Predviđanje broja dana potrebnih da gradska služba 311 u Njujorku reši (zatvori) prijavu pacova u siromašnim gradskim blokovima. Model koristi samo podatke poznate u trenutku podnošenja prijave: vreme prijave, lokaciju, deo grada, stopu siromaštva i udeo podstanara u bloku, kao i trenutno opterećenje službe.

- **Tip problema:** regresija
- **Ciljna promenljiva:** `days_to_close`
- **Jedan primer:** jedna prijava pacova službi 311

## Podaci

- **Izvor:** [Rat Complaints in High-Poverty Blocks (Kaggle)](https://www.kaggle.com/datasets/edkearth/rat-complaints-high-poverty)
- **Autor:** EDK (edk.earth), na osnovu javnih 311 skupova podataka gradova SAD
- **Licenca:** [CC BY-SA 4.0](https://creativecommons.org/licenses/by-sa/4.0/)

CSV fajl se nalazi u folderu `data/`. Projekat koristi samo prijave iz Njujorka (~22.600 redova).

## Struktura

```
nyc-rat-complaints-ml/
├── data/          # originalni skup podataka (Kaggle)
├── notebooks/     # Jupyter notebook sa analizom i modelima
├── requirements.txt
└── README.md
```

## Pokretanje

Potreban je Python 3.9+.

```bash
python -m venv .venv
# Windows:
.venv\Scripts\activate
# Linux/macOS:
source .venv/bin/activate

pip install -r requirements.txt
jupyter notebook
```

Zatim otvoriti notebook iz foldera `notebooks/` i izvršiti sve ćelije redom (Kernel → Restart & Run All).
