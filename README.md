# Predviđanje mesečne kirije stanova u gradovima Poljske

Projekat iz predmeta veštačka inteligencija (I projekat).

## Problem

Predviđanje mesečne kirije (PLN) stana na osnovu njegovih karakteristika (kvadratura, broj soba, sprat, godina gradnje, opremljenost) i urbane okoline (grad, udaljenost od centra, broj i udaljenost obližnjih škola, ambulanti, restorana, apoteka...).

- **Tip problema:** regresija
- **Ciljna promenljiva:** `price` (mesečna kirija u PLN)
- **Jedan primer:** jedan stan oglašen za izdavanje

## Podaci

- **Izvor:** [Apartment Prices in Poland (Kaggle)](https://www.kaggle.com/datasets/krzysztofjamroz/apartment-prices-in-poland), autor Krzysztof Jamroz
- **Licenca:** Apache 2.0
- Koriste se fajlovi sa oglasima za izdavanje (`data/apartments_rent_pl_*.csv`), mesečni snimci od novembra 2023. do juna 2024.

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
