# Najważniejsze aktywa

Za krytyczne uznaliśmy te aktywa, bez których firma nie może świadczyć usług albo których ujawnienie uderza bezpośrednio w klientów: bazy danych, kod źródłowy, serwery i wiedzę pracowników.

## Rejestr aktywów

| Nr | Aktywo | Opis | Właściciel | Znaczenie |
|---|---|---|---|---|
| 1 | Kod źródłowy projektów | Repozytoria i pliki źródłowe stron tworzonych dla klientów | Tech Lead / Główny Programista | Krytyczne |
| 2 | Bazy danych klientów i aplikacji | Dane klientów, dane uwierzytelniające i dane produkcyjne wdrożonych stron | Administrator Baz Danych / DevOps | Krytyczne |
| 3 | System CRM | Historia kontaktów, dane kontaktowe i umowy z klientami | Specjalista ds. Sprzedaży / Manager Projektu | Wysokie |
| 4 | Serwer plików | Dokumentacja projektowa, grafiki, materiały od klientów | Administrator IT | Wysokie |
| 5 | Komputery użytkowników | Laptopy 10 osób pracujących hybrydowo | Wszyscy pracownicy / Administrator IT | Wysokie |
| 6 | Serwery | Środowiska testowe stron i systemy wewnętrzne | Administrator IT / DevOps | Krytyczne |
| 7 | Usługi chmurowe | Hosting, narzędzia SaaS do projektów i zasobów | Administrator IT | Wysokie |
| 8 | Poczta elektroniczna | Komunikacja z klientami, partnerami i wewnątrz firmy | Administrator IT | Wysokie |
| 9 | Oprogramowanie projektowe | Licencjonowane narzędzia UI/UX i 3D (Figma, UXPin, Blender) | Senior UI/UX Designer / Główny Grafik | Wysokie |
| 10 | Wiedza pracowników | Unikalne kompetencje 10-osobowego zespołu | Zarząd / Wszyscy pracownicy | Krytyczne |

Dlaczego wiedza pracowników jest krytyczna: w 10-osobowej firmie często tylko jedna osoba zna dany system. Jej odejście lub choroba może zatrzymać pracę bardziej niż awaria sprzętu (ryzyko R16).

## Zagrożenia i podatności

| Aktywo | Zagrożenie | Podatność | Możliwe konsekwencje |
|---|---|---|---|
| Kod źródłowy | Nieuczciwy pracownik lub nieautoryzowany dostęp z zewnątrz | Brak ścisłej kontroli wersji, brak DLP | Kradzież własności intelektualnej, utrata projektów, opóźnienia wdrożeń, spadek reputacji |
| Bazy danych | Atak hakerski, SQL Injection | Przestarzałe oprogramowanie bazy, brak testów penetracyjnych, słabo przetestowane interfejsy aplikacji | Wyciek danych klientów, naruszenie RODO, kary finansowe |
| Komputery użytkowników | Phishing, złośliwe oprogramowanie | Brak aktualnego antywirusa, brak polityki haseł i MFA | Przejęcie stacji roboczej, zaszyfrowanie danych |
| Serwery | Awaria lub cyberatak | Brak aktualizacji, brak monitoringu, brak aktualnego backupu | Niedostępność środowisk, utrata danych, przerwa w usługach, straty finansowe |
| Usługi chmurowe | Błędna konfiguracja | Domyślne dane logowania, publiczne uprawnienia, brak MFA dla administratorów | Dostęp osób trzecich do danych produkcyjnych, zmiana kodu stron klientów, przejęcie infrastruktury chmurowej |

Pełna ocena ryzyka jest w [risks.md](risks.md).
