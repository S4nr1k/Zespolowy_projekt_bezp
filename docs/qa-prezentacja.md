# Przygotowanie do pytań

Odpowiedzi na pytania, które mogą paść podczas prezentacji. Każdy członek zespołu powinien je znać.

**Dlaczego wyciek danych z bazy (R1) oceniliście najwyżej?**
Prawdopodobieństwo 4, bo baza ma przestarzałe oprogramowanie i nikt nie robił testów penetracyjnych, a SQL Injection to jeden z najczęstszych ataków na strony. Skutek 5, bo chodzi o dane osobowe użytkowników klientów: zgłoszenie do UODO, kary, roszczenia i utrata klientów, dla małej firmy nawet koniec działalności.

**Dlaczego MFA jako pierwsze zabezpieczenie?**
Bo obniża najwięcej ryzyk naraz (R3, R5, R7, R8) przy najniższym koszcie. Większość przejęć kont zaczyna się od wykradzionego hasła, a samo hasło przy MFA nie wystarcza. Wdrożenie zajmuje dzień, a nie miesiące.

**Dlaczego segmentacja sieci, skoro firma ma tylko 10 osób?**
Bo liczba osób nie zmienia tego, że jeden zainfekowany laptop albo drukarka z domyślnym hasłem bez segmentacji widzi wszystkie serwery. Podział na VLAN-y sprawia, że infekcja jednego urządzenia nie oznacza dostępu do kopii i bazy.

**Co się stanie, jeśli MFA przestanie działać albo ktoś je obejdzie?**
Zostają kolejne warstwy: najmniejsze uprawnienia (przejęte konto widzi tylko swój zakres), osobne konta administracyjne, monitoring logowań z nowych lokalizacji i kopie niezmienialne, których przejęte konto nie usunie. Projekt nie opiera się na jednym zabezpieczeniu.

**Co się stanie, jeśli przestaną działać kopie zapasowe?**
Wykryje to kwartalny test odtwarzania, dlatego jest w rekomendacjach razem z samą kopią. Kopia, której nikt nie próbował odtworzyć, daje fałszywe poczucie bezpieczeństwa.

**Które rozwiązanie wdrożylibyście jako pierwsze?**
MFA na kontach administratorów, GitHub, chmurze, poczcie i VPN. Zaraz potem aktualizacja bazy i test penetracyjny, bo dotyczą ryzyka numer 1.

**Z którego ryzyka organizacja może świadomie zrezygnować?**
Z R6 (awaria CRM w SaaS, poziom 6) i R23 (szczegóły widoczne na zdjęciach, poziom 6). Skutek jest krótki i ograniczony, a pełne zabezpieczenie kosztowałoby więcej niż strata. Wystarczy eksport danych z CRM i zasada sprawdzania zdjęć przed publikacją.

**Dlaczego dla R10 wybraliście unikanie, a nie ograniczanie ryzyka?**
Bo sekret w kodzie da się całkowicie wyeliminować: trzyma się go w menedżerze sekretów, a GitHub blokuje commit z hasłem. Skoro można usunąć źródło ryzyka, nie ma sensu tylko go zmniejszać.

**Co byłoby największym problemem podczas rzeczywistego incydentu?**
Brak centralnych logów. Bez nich nie wiadomo, od kiedy trwał atak i jakie dane wyciekły, a od tego zależy zgłoszenie do UODO w 72 godziny. Drugi problem to ludzie: w małej firmie te same osoby muszą reagować na incydent, rozmawiać z klientem i dalej prowadzić projekty.

**Dlaczego produkcja jest w chmurze, a nie w biurze?**
Bo strony klientów muszą działać niezależnie od biura (awaria prądu, internetu, sprzętu). Ceną jest to, że konfiguracja chmury i konta administratorów stają się krytyczne, dlatego R5 i R7 są wysoko w rejestrze.
