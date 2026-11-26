# Bezpieczeństwo danych i wykorzystanie AI

## Najważniejsze dane

| Cecha | Baza klientów i aplikacji | Kod źródłowy projektów | Dokumentacja i materiały projektowe |
|---|---|---|---|
| Gdzie jest | Baza w chmurze hostingowej, dostęp tylko przez aplikację po HTTPS | Prywatne repozytoria GitHub, kopie robocze na laptopach programistów | Serwer plików w biurze (VLAN 20), Figma i UXPin w chmurze |
| Kto ma dostęp | Aplikacja przez konto bez praw administratora bazy, administrator baz i DevOps. Programiści tylko do kopii testowej z danymi zanonimizowanymi | Programiści według projektów, Tech Lead jako właściciel organizacji, konto CI/CD z tokenem o minimalnych uprawnieniach | Grupy projektowe, graficy, manager projektu. Klient tylko przez link do swojego prototypu, z hasłem i datą ważności |
| Szyfrowanie | TLS, szyfrowanie bazy i kopii, hasła tylko jako skróty (bcrypt lub Argon2) | HTTPS lub SSH, szyfrowane dyski laptopów. Hasła i klucze API nigdy w repozytorium, tylko w menedżerze sekretów | Szyfrowane dyski i kopia zewnętrzna. Materiały z NDA w osobnych, ograniczonych katalogach |
| Jak długo przechowywać | Przez czas umowy i okres z przepisów, potem usunięcie lub przekazanie klientowi (RODO, minimalizacja) | Przez czas utrzymania strony, potem przekazanie klientowi zgodnie z umową | Przez czas projektu i gwarancji. Umowy i dokumenty rozliczeniowe 5 lat |
| Kopia zapasowa | Codziennie, szyfrowana i niezmienialna w osobnym koncie (3-2-1), test odtwarzania co kwartał | Cotygodniowy eksport repozytoriów do kopii zewnętrznej, dodatkowo klony u programistów | Serwer kopii w biurze i chmura, jedna kopia offline. Eksport z Figma i UXPin co tydzień |
| Skutek ujawnienia (poufność) | Naruszenie RODO, zgłoszenie do UODO w 72 h, kary, roszczenia | Kradzież własności intelektualnej, naruszenie umów, a przy kluczach w kodzie dostęp do produkcji | Ujawnienie projektów przed premierą, naruszenie NDA, kary umowne |
| Skutek modyfikacji (integralność) | Fałszywe dane, podmienione dane logowania lub numery kont, oszustwa | Złośliwy kod na stronach klientów (R19), atak na ich użytkowników | Praca na złej wersji projektu, spory o zakres |
| Skutek utraty dostępu (dostępność) | Strony klientów nie działają, kary za naruszenie SLA | Brak możliwości wdrażania poprawek, także bezpieczeństwa | Zatrzymanie pracy grafików, niedotrzymane terminy |

## Wykorzystanie AI

Firma może używać asystenta kodu (programiści), czatu AI (wszyscy pracownicy) i chatbota na stronach klientów (użytkownicy spoza firmy).

| Pytanie | Odpowiedź |
|---|---|
| Jakie dane mogą trafiać do AI? | Fragmenty kodu i komunikaty błędów, treści stron, opisy projektów, briefy i dokumenty od klientów, a w chatbocie pytania użytkowników stron |
| Czy są wśród nich dane poufne? | Tak: kod klientów, klucze API i hasła w konfiguracji, dane osobowe przy debugowaniu, umowy i projekty z NDA, dane wpisywane w chatbocie |
| Kto może korzystać? | Asystent kodu: programiści. Czat: wszyscy, tylko na kontach firmowych z MFA. Chatbot: użytkownicy stron, dlatego ma najwęższe uprawnienia |
| Co można przypadkiem ujawnić? | Plik .env z hasłami, zrzut bazy z danymi klientów, całą umowę, szczegóły projektu przed premierą, zrzut ekranu z danymi logowania |
| Czy wynik AI jest automatycznie poprawny? | Nie. AI może podać nieprawdziwe fakty, kod z podatnościami, nieistniejące biblioteki albo treść naruszającą prawa autorskie. Odpowiada za niego pracownik, który go użył |

**Zasady dla organizacji.** Tylko zatwierdzone narzędzia na kontach firmowych, z umową powierzenia i wyłączonym trenowaniem na danych firmy, bez prywatnych kont. Zakaz wklejania haseł, kluczy, danych osobowych i dokumentów z NDA bez zgody klienta. Kod z AI przechodzi ten sam przegląd i testy co kod pisany ręcznie. Treści sprawdza człowiek przed publikacją. Chatbot informuje, że jest AI (AI Act), i nie ma dostępu do bazy klientów ani do działań na kontach. Szkolenie przed nadaniem dostępu, przegląd zasad co pół roku.

| ID | Ryzyko | Zabezpieczenie | Poziom |
|---|---|---|---|
| R24 | Ujawnienie danych poufnych lub kodu przez publiczne narzędzie AI | Konta firmowe z umową powierzenia, zakaz danych poufnych, blokada niezatwierdzonych narzędzi, szkolenie | 12 |
| R25 | Kod z AI z podatnością lub z podstawioną biblioteką | Przegląd kodu, SAST i skanowanie zależności w CI, lista zatwierdzonych bibliotek | 12 |
| R26 | Prompt injection w chatbocie | Brak dostępu chatbota do bazy i kont, filtr odpowiedzi, logowanie rozmów, testy | 8 |
| R27 | Naruszenie praw autorskich przez treści z AI | Sprawdzanie treści, informowanie klienta o użyciu AI, licencje narzędzi | 9 |
