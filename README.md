# Prognoza pogody dla podróżników (Flask + SQLite + Folium)

Aplikacja webowa do planowania podróży z uwzględnieniem pogody na trasie.  
Wpisujesz **start**, **cel** (i opcjonalne punkty pośrednie), wybierasz **krok próbkowania trasy** oraz **środek transportu** — aplikacja:
- wyznacza trasę,
- pobiera prognozę pogody na najbliższe 7 dni wzdłuż trasy,
- wybiera **najlepsze dni** do przejazdu (najmniejsze ryzyko),
- rysuje **mapę** oraz pokazuje tabelę z podsumowaniem,
- zapisuje wyszukiwania do **bazy SQLite** (zakładka *Historia*).

> Edukacyjny projekt końcowy: Flask + SQLAlchemy + Jinja2 + Requests + Pandas + Folium  
> Zewnętrzne usługi: **Open-Meteo**, **Nominatim (OpenStreetMap)**, **OSRM**.

![Podgląd](docs/screenshot.png)

---

## Spis treści
- [Wymagania](#wymagania)
- [Szybki start (lokalnie)](#szybki-start-lokalnie)
- [Jak używać](#jak-używać)
- [Architektura / co jest w środku](#architektura--co-jest-w-środku)
- [Endpointy](#endpointy)
- [Struktura katalogów](#struktura-katalogów)
- [Źródła danych i limity](#źródła-danych-i-limity)
- [Rozwiązywanie problemów](#rozwiązywanie-problemów)
- [Licencja](#licencja)

---

## Wymagania
- Python 3.9+ (projekt działa na 3.9)
- System: macOS / Linux / Windows
- Konto GitHub (jeśli chcesz tylko uruchomić lokalnie, nie jest wymagane)

---

## Szybki start (lokalnie)

```bash
# 1) Klon repo (albo pobierz ZIP z GitHuba)
git clone https://github.com/hypen/projekt_koncowy_prognozaflask.git
cd projekt_koncowy_prognozaflask

# 2) Virtualenv
python3 -m venv .venv
# macOS/Linux:
source .venv/bin/activate
# Windows (PowerShell):
# .venv\Scripts\Activate.ps1

# 3) Biblioteki
pip install -r requirements.txt

# 4) Start serwera
python app.py
# Aplikacja będzie pod: http://127.0.0.1:5000/
