# Rejestr ryzyka

Pełny rejestr w arkuszu: [risk-register/risk-register.xlsx](../risk-register/risk-register.xlsx).

## Metoda oceny

Poziom ryzyka = prawdopodobieństwo × skutek, oba w skali 1 do 5.

| Poziom | Ocena | Postępowanie |
|---|---|---|
| 15 do 25 | Wysokie | Działania w pierwszej kolejności |
| 8 do 14 | Średnie | Działania planowane w ciągu kilku miesięcy |
| 1 do 7 | Niskie | Można świadomie zaakceptować i monitorować |

Prawdopodobieństwo oceniamy według tego, jak łatwo przeprowadzić atak i czy firma ma znane podatności. Skutek według tego, czy dotyka klientów (dane, ich strony) i czy grozi karami z RODO lub zatrzymaniem pracy.

## TOP 5

| Miejsce | ID | Ryzyko | Poziom | Dlaczego wysoko |
|---|---|---|---|---|
| 1 | R1 | Wyciek danych klientów z bazy przez atak na przestarzałe oprogramowanie | 20 | Przestarzała baza i brak testów to łatwy cel (4), a wyciek danych osobowych oznacza RODO, kary i utratę klientów (5) |
| 2 | R3 | Przejęcie laptopa pracownika przez phishing lub malware | 16 | Praca hybrydowa i brak MFA oraz aktualnego antywirusa, a z laptopa jest dostęp do kodu i serwerów |
| 3 | R5 | Nieautoryzowany dostęp do chmury przez błędną konfigurację | 16 | Domyślne hasła i brak MFA u administratorów chmury, a w chmurze są produkcyjne strony klientów |
| 4 | R10 | Hasła i klucze API w repozytorium GitHub | 16 | Częsty błąd programistów, a klucz w kodzie daje bezpośredni dostęp do produkcji |
| 5 | R22 | Spear phishing na podstawie informacji publicznych | 16 | Nazwiska, stanowiska, technologie i klienci są publiczne w portfolio, więc atak łatwo dopasować |

Na poziomie 15 są jeszcze R2, R4, R7, R8, R11 i R19. Do TOP 5 wybraliśmy ryzyka z wyższym prawdopodobieństwem, bo przy równym skutku częstsze zdarzenie jest pilniejsze.

## Pełny rejestr

| ID | Ryzyko | Praw. | Skutek | Poziom | Źródło |
|---|---|---|---|---|---|
| R1 | Wyciek danych klientów i aplikacji produkcyjnych przez atak na przestarzałe oprogramowanie bazodanowe | 4 | 5 | 20 | Zajęcia 1 |
| R2 | Kradzież lub usunięcie kodu źródłowego przez nieuczciwego pracownika (brak kontroli wersji i DLP) | 3 | 5 | 15 | Zajęcia 1 |
| R3 | Przejęcie laptopa pracownika przez phishing lub malware w pracy hybrydowej | 4 | 4 | 16 | Zajęcia 1 |
| R4 | Awaria serwerów | 3 | 5 | 15 | Zajęcia 1 |
| R5 | Nieautoryzowany dostęp do chmury i danych produkcyjnych przez błędną konfigurację | 4 | 4 | 16 | Zajęcia 1 |
| R6 | Utrata ciągłości pracy CRM przez awarię dostawcy SaaS lub błąd użytkownika | 2 | 3 | 6 | Zajęcia 1 |
| R7 | Przejęcie konta administratora i pełna kompromitacja infrastruktury | 3 | 5 | 15 | Zajęcia 3 |
| R8 | Atak na VPN lub dostęp zdalny | 3 | 5 | 15 | Zajęcia 3 |
| R9 | Ruch boczny w sieci z powodu braku segmentacji | 3 | 4 | 12 | Zajęcia 3 |
| R10 | Wyciek haseł i kluczy API z repozytorium GitHub | 4 | 4 | 16 | Zajęcia 3 |
| R11 | Ransomware szyfruje serwer plików i kopie zapasowe | 3 | 5 | 15 | Zajęcia 3 |
| R12 | Przejęcie urządzeń IoT z domyślnymi hasłami | 3 | 3 | 9 | Zajęcia 3 |
| R13 | Kradzież lub zgubienie laptopa bez szyfrowania dysku | 3 | 4 | 12 | Zajęcia 3 |
| R14 | Atak niewykryty z powodu braku monitoringu | 4 | 3 | 12 | Zajęcia 3 |
| R15 | Dostęp do poczty i CRM z niezabezpieczonych telefonów | 3 | 3 | 9 | Zajęcia 3 |
| R16 | Utrata wiedzy po odejściu kluczowego pracownika | 3 | 4 | 12 | Zajęcia 3 |
| R17 | Aktywne konta byłych pracowników i wykonawców | 3 | 4 | 12 | Zajęcia 4 |
| R18 | Usunięcie danych w chmurze razem z kopią po przejęciu konta | 2 | 5 | 10 | Zajęcia 4 |
| R19 | Przejęcie konta CI/CD i złośliwy kod na stronach klientów | 3 | 5 | 15 | Zajęcia 4 |
| R20 | Praca na prywatnych urządzeniach bez kontroli | 4 | 3 | 12 | Zajęcia 4 |
| R21 | Przestarzałe oprogramowanie kamery i drukarki | 3 | 3 | 9 | Zajęcia 4 |
| R22 | Spear phishing na podstawie informacji publicznych | 4 | 4 | 16 | Zajęcia 4 |
| R23 | Ujawnienie szczegółów wewnętrznych na zdjęciach | 2 | 3 | 6 | Zajęcia 4 |
| R24 | Ujawnienie danych poufnych lub kodu klientów przez wklejenie do publicznego narzędzia AI | 3 | 4 | 12 | Zajęcia 5 |
| R25 | Wdrożenie kodu z AI z podatnością lub z podstawioną biblioteką | 3 | 4 | 12 | Zajęcia 5 |
| R26 | Prompt injection w chatbocie na stronie klienta | 2 | 4 | 8 | Zajęcia 5 |
| R27 | Naruszenie praw autorskich przez treści lub grafiki z AI | 3 | 3 | 9 | Zajęcia 5 |

## Strategia postępowania z TOP 5

| ID | Strategia | Uzasadnienie |
|---|---|---|
| R1 | Reduce, ryzyko resztkowe Transfer | Bazy nie da się zlikwidować, to podstawa usług. Ograniczamy: aktualizacje, WAF, testy penetracyjne, szyfrowanie, najmniejsze uprawnienia. Koszty obsługi naruszenia i roszczenia przenosimy na ubezpieczenie cyber i umowy z klientami |
| R3 | Reduce | Praca hybrydowa to model firmy, więc jej nie unikamy. MFA, EDR, szyfrowanie dysków, brak praw administratora i szkolenia tanio obniżają prawdopodobieństwo i skutek |
| R5 | Reduce | Chmura jest niezbędna. Lista kontrolna, zasoby prywatne domyślnie, alerty przy zmianie na publiczne, przegląd uprawnień co kwartał |
| R10 | Avoid | Eliminujemy samo działanie: sekrety tylko w menedżerze sekretów, a ochrona przed wypchnięciem sekretu w GitHub blokuje taki commit. Bez sekretów w kodzie nie ma czego wykraść |
| R22 | Reduce | Portfolio i kontakt są firmie potrzebne, więc informacji nie da się ukryć całkiem. Mniej szczegółów na stronie, SPF, DKIM, DMARC, szkolenia i potwierdzanie przelewów drugim kanałem |

## Ryzyka, które można świadomie zaakceptować

R6 (awaria CRM w SaaS, poziom 6) i R23 (szczegóły na zdjęciach, poziom 6). Skutek jest ograniczony i krótkotrwały, a pełne zabezpieczenie kosztowałoby więcej niż możliwa strata. Wystarczy eksport danych z CRM i prosta zasada sprawdzania zdjęć przed publikacją.
