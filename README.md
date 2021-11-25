# Registr odcizených jízdních kol

Krádež kol je častý a nepříjemný problém nejenom ve velkých městech. Existuje veřejný registr [Bike Index](https://bikeindex.org), kam mohou majitelé nahrát detailní informace o svých odcizených dvoukolých miláčcích.

Policejní oddělení chce zefektivnit řešení případů odcizených kol. Z tohoto důvodu požadují vytvoření webové aplikace pro snadné nahlížení do registru.

## Funkční požadavky
Jako policista obsluhující webovou aplikaci chci mít možnost:

- [ ] Zobrazit přehled případů odcizených kol.
- [ ] Zobrazit prvních 20 odcizených kol s podporou stránkování po 20.
- [ ] Zobrazit aktuální počet všech nahlášených případů.
- [ ] Zobrazit informace o každém nahlášeném případu:
    - [ ] Rok výroby
    - [ ] Jméno modelu jízdního kola
    - [ ] Barva
    - [ ] Výrobní číslo
    - [ ] Datum krádeže
    - [ ] Místo krádeže
    - [ ] Náhled fotografie
- [ ] Filtrovat přehled podle barvy rámu jízního kola (black, blue, green ...).
- [ ] Filtrovat přehled podle výrobního čísla (libovolný text).
- [ ] Vidět spinner dokud nejsou načtena data z registru.
- [ ] Vidět upozornění, když neexistují žádná data splňující kritéria vyhledávání.
- [ ] Vidět upozornění v případě chyby při vykonávání vyhledávání.

## Technické požadavky

- React
- styled-components
- TypeScript výhodou

## Data

Pro získání dat použijte veřejně dostupný registr kol [Bike Index](https://bikeindex.org), konkrétně endpoint `/v3/search/`. Dokumentace k API je dostupná [ZDE](https://bikeindex.org/documentation/api_v3#!/search/GET_version_search_format_get_0).

### Ukázka HTTP dotazu
```
https://bikeindex.org:443/api/v3/search?page=1&per_page=25&colors=black&location=IP&distance=10&stolenness=stolen
```

### Ukázka HTTP odpovědi

```
{
  "bikes": [
    {
      "date_stolen": 1637848800,
      "description": "Has pinhead locks on the wheels n seat post ",
      "frame_colors": [
        "Black",
        "Blue"
      ],
      "frame_model": "Storm",
      "id": 399113,
      "manufacturer_name": "Norco Bikes",
      "serial": "AJ61004359",
      "thumb": "https://files.bikeindex.org/uploads/Pu/145021/small_3AE2CCD0-8359-4447-AD5E-292EEDD38E75.jpeg",
      "title": "2017 Norco Bikes Storm",
      "year": 2017
    },
  ]
}
```


## Váš úkol
Vaším úkolem je vytvořit jednoduchou webovou aplikaci s použitím frameworku React, která musí obsahovat výše uvedené požadavky. Jakékoliv požadavky navíc, volte podle svého uvážení.

