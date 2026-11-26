# Rekomendacje

## Pięć działań w pierwszej kolejności

| Nr | Działanie | Ryzyka | Termin | Dlaczego tak wcześnie |
|---|---|---|---|---|
| 1 | MFA na wszystkich kontach, najpierw administratorzy, GitHub, chmura, poczta i VPN | R3, R5, R7, R8 | Od razu | Najtańsze i najszybsze, a blokuje większość przejęć kont po wycieku hasła |
| 2 | Aktualizacja bazy danych, WAF i test penetracyjny wszystkich stron klientów | R1 | 1 miesiąc | Ryzyko numer 1 w rejestrze (20), a podatność jest już znana |
| 3 | Sekrety tylko w menedżerze sekretów, ochrona przed wypchnięciem sekretu i skan historii repozytoriów | R10, R19 | 1 miesiąc | Klucz w kodzie to gotowy dostęp do produkcji dla każdego, kto zobaczy repozytorium |
| 4 | Kopie 3-2-1 z kopią niezmienialną i offline, kwartalny test odtwarzania | R4, R11, R18 | 1 miesiąc | Dziś firma nie ma aktualnego backupu, więc awaria lub ransomware oznacza trwałą utratę danych |
| 5 | EDR i szyfrowanie dysków na wszystkich laptopach, brak praw administratora | R3, R13 | 3 miesiące | Laptop w pracy hybrydowej to najczęstszy punkt wejścia atakującego |

## Kolejne działania

| Nr | Działanie | Ryzyka | Termin |
|---|---|---|---|
| 6 | Szkolenie z phishingu i AI dla całego zespołu, SPF, DKIM, DMARC, potwierdzanie przelewów drugim kanałem | R22, R24 | 3 miesiące |
| 7 | Polityka AI z listą zatwierdzonych narzędzi i przeglądem kodu z AI | R24, R25, R27 | 3 miesiące |
| 8 | Centralny monitoring i alerty, procedura incydentu ćwiczona raz w roku | R14, R1 | 6 miesięcy |
| 9 | Kwartalny przegląd uprawnień i kont byłych pracowników, segmentacja VLAN | R9, R17 | 6 miesięcy |

## Kolejność wynika z trzech kryteriów

1. Poziom ryzyka, którego działanie dotyczy.
2. Koszt i czas wdrożenia. MFA zajmuje dzień, centralny monitoring kilka miesięcy.
3. Liczba ryzyk, które jedno działanie obniża naraz.
