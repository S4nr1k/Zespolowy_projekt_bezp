# Bezpieczeństwo infrastruktury Witchak Modeling

Projekt zespołu **Ziemniaczki** w ramach przedmiotu Zespołowy projekt bezpieczeństwa II (WSB Merito, zima 2026/2027).

Analizujemy bezpieczeństwo małej firmy tworzącej strony internetowe: jej środowisko IT, najważniejsze aktywa i ryzyka, zabezpieczenia, sposób reagowania na incydent oraz rekomendacje.

## Zespół

| Osoba | Nr albumu |
|---|---|
| Michał Szyksznia | 163342 |
| Kamil Witczak | 163344 |
| Oskar Wilk | 163343 |
| Ihor Skrypnyk | 165132 |

Role w zespole i ich zakres opisuje [organization.md](organization.md).

## Projekt w skrócie

- **Organizacja:** Witchak Modeling, 10 osób, praca hybrydowa, projektowanie stron internetowych.
- **Najważniejsze aktywa:** bazy danych klientów, kod źródłowy projektów, serwery i wiedza pracowników.
- **TOP 5 ryzyk:** wyciek danych klientów z bazy (R1, 20), przejęcie laptopa pracownika (R3, 16), błędna konfiguracja chmury (R5, 16), hasła i klucze w repozytorium (R10, 16), spear phishing na podstawie informacji publicznych (R22, 16).
- **Rejestr ryzyka:** 27 ryzyk (R1 do R27), skala prawdopodobieństwo × skutek od 1 do 5.
- **Incydent:** wyciek danych klientów przez SQL Injection, opisany w sześciu etapach reakcji.

## Struktura repozytorium

```text
security-project/
├── README.md                    (bez zmian)
├── docs/
│   ├── README.md                ten plik, opis projektu
│   ├── organization.md          firma, zespół i podział ról
│   ├── scope.md                 zakres projektu i przyjęte założenia
│   ├── assets.md                rejestr aktywów, zagrożenia i podatności
│   ├── architecture.md          środowisko IT, przepływy danych, zabezpieczenia
│   ├── risks.md                 rejestr ryzyka R1 do R27, TOP 5, strategie
│   ├── cloud-mobile-iot.md      chmura, urządzenia mobilne, IoT, informacje publiczne
│   ├── data-ai.md               bezpieczeństwo danych i wykorzystanie AI
│   ├── incident-response.md     scenariusz incydentu i reakcja organizacji
│   ├── recommendations.md       rekomendacje i kolejność wdrożenia
│   └── qa-prezentacja.md        uzasadnienia decyzji, przygotowanie do pytań
├── diagrams/
│   ├── architecture.drawio      diagram środowiska (edycja w app.diagrams.net)
│   └── architecture.png         ten sam diagram jako obraz
├── risk-register/
│   └── risk-register.xlsx       pełny rejestr ryzyka w arkuszu
├── presentation/                materiały do prezentacji
└── pliki z zajęć 1 do 5         oryginalne wyniki z kolejnych zajęć, bez zmian
```

## Od czego zacząć czytanie

1. [organization.md](organization.md) i [scope.md](scope.md), czyli kogo chronimy i w jakim zakresie.
2. [architecture.md](architecture.md) z diagramem, czyli jak wygląda środowisko.
3. [assets.md](assets.md) i [risks.md](risks.md), czyli co jest cenne i co mu zagraża.
4. [recommendations.md](recommendations.md), czyli co firma powinna zrobić najpierw.

## Historia prac

| Zajęcia | Zakres | Gdzie teraz |
|---|---|---|
| 1 | Organizacja, zespół, aktywa, zagrożenia, pierwsze ryzyka R1 do R6 | organization.md, scope.md, assets.md, risks.md |
| 2 | Opis organizacji, dane i systemy, przykładowe zagrożenia | organization.md, scope.md |
| 3 | Diagram, przepływy danych, zabezpieczenia, ryzyka R7 do R16 | architecture.md, risks.md, diagrams/ |
| 4 | Chmura, urządzenia mobilne, IoT, informacje publiczne, ryzyka R17 do R23 | cloud-mobile-iot.md, risks.md |
| 5 | Dane, AI, incydent, strategia ryzyka, ryzyka R24 do R27, rekomendacje | data-ai.md, incident-response.md, risks.md, recommendations.md |
