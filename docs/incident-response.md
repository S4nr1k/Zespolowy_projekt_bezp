# Reagowanie na incydent

## Scenariusz: wyciek danych klientów przez SQL Injection

Wybraliśmy ten scenariusz, bo odpowiada ryzyku R1, najwyżej ocenionemu w rejestrze (poziom 20). Atakujący wykorzystuje podatny formularz na stronie klienta i pobiera z bazy dane użytkowników. Firma jest tu podmiotem przetwarzającym, a administratorem danych jest jej klient, co ma znaczenie przy powiadomieniach.

## Przebieg reakcji

| Etap | Działania | Kto |
|---|---|---|
| 1. Wykrycie | Alert z monitoringu: nietypowo duża liczba zapytań do bazy i błędy SQL w logach WAF. Inne możliwe źródła: zgłoszenie klienta, skargi użytkowników na phishing, dane wystawione na forum. Pierwsza osoba, która zauważy problem, zgłasza go Liderowi Projektu, który zakłada rejestr incydentu z godziną wykrycia | Każdy pracownik, Lider Projektu |
| 2. Analiza | Zabezpieczenie dowodów przed zmianami: kopia logów serwera WWW, WAF i bazy, migawka maszyny. Ustalenie wektora (który formularz, jakie zapytania), zakresu (tabele, liczba rekordów, czy były hasła i dane osobowe), okresu i tego, czy atakujący coś zostawił (konta, webshell) | Specjalista ds. aplikacji, Administrator |
| 3. Ograniczenie | Strona w trybie serwisowym albo wyłączenie samego formularza, reguła WAF blokująca wzorzec ataku i adresy atakującego. Zmiana hasła konta aplikacji do bazy i kluczy API, unieważnienie sesji. Sprawdzenie, czy ten sam kod nie działa na stronach innych klientów | Administrator, Specjalista ds. aplikacji |
| 4. Usunięcie przyczyny | Poprawka kodu: zapytania parametryzowane i walidacja danych. Aktualizacja przestarzałej bazy. Usunięcie kont i plików dodanych przez atakującego, skan podatności wszystkich stron z tym samym szablonem | Specjalista ds. aplikacji |
| 5. Przywrócenie | Wdrożenie poprawionej wersji po testach, przywrócenie danych z kopii, jeśli zostały zmienione. Wymuszenie zmiany haseł użytkownikom strony, wzmożony monitoring przez 30 dni | Administrator |
| 6. Wnioski | Spotkanie w ciągu 2 tygodni i krótki raport: co zadziałało, ile trwało wykrycie i reakcja. Zmiany w procesach i aktualizacja rejestru ryzyka | Lider Projektu, cały zespół |

## Powiadomienia (RODO)

Firma powiadamia klienta, czyli administratora danych, bez zbędnej zwłoki (art. 33 ust. 2 RODO). Klient zgłasza naruszenie do UODO w ciągu 72 godzin od stwierdzenia, a przy wysokim ryzyku dla osób informuje też użytkowników (art. 34). Komunikat przygotowuje Lider Projektu razem z klientem.

## Zmiany po incydencie

Test penetracyjny przed każdym wdrożeniem i raz w roku, skanowanie SAST w CI, WAF dla wszystkich stron, harmonogram aktualizacji baz, procedura incydentu ćwiczona raz w roku, aktualizacja oceny R1.

## Co byłoby największym problemem w rzeczywistości

Brak centralnych logów (R14). Bez nich nie da się ustalić, od kiedy trwał atak i jakie dane wyciekły, a na tej podstawie podejmuje się decyzję o zgłoszeniu do UODO i powiadomieniu użytkowników. W 10-osobowej firmie problemem byłby też czas: te same osoby muszą jednocześnie gasić incydent, rozmawiać z klientem i dalej prowadzić projekty.
