# Chmura, urządzenia mobilne, IoT i informacje publiczne

## Chmura

| Zagadnienie | Ustalenia |
|---|---|
| Usługi i dane | Hosting produkcyjny stron, GitHub, CRM, poczta, zarządzanie projektami, Figma i UXPin, zewnętrzna kopia zapasowa. W chmurze są: kod źródłowy, baza klientów i aplikacji, projekty graficzne, umowy i korespondencja |
| Dostęp i konta kluczowe | Programiści, graficy, manager projektu i sprzedaż mają dostęp do swoich narzędzi. Najważniejsze konta: właściciel hostingu i organizacji GitHub, administratorzy poczty i CRM, konta serwisowe CI/CD i bazy |
| Błędne konfiguracje | Publiczne repozytorium lub zasób, otwarty port bazy, domyślne hasła, zbyt szerokie role, publiczne linki do prototypów, konta byłych pracowników |
| Backup | Baza kopiowana codziennie, kopia szyfrowana i niezmienialna w osobnym koncie (3-2-1). Repozytoria i dane SaaS eksportowane co tydzień. Test odtwarzania co kwartał |
| MFA | Na wszystkich kontach, obowiązkowo u administratorów, w GitHub, poczcie, CRM i przy dostępie do kopii |
| Monitoring | Logowania administratorów i z nowych lokalizacji, zmiany uprawnień, nowe klucze API, zasoby zmienione na publiczne, masowe pobieranie danych, force push, usunięcie kopii |

| ID | Ryzyko | Zabezpieczenie |
|---|---|---|
| R5 | Błędna konfiguracja chmury | Lista kontrolna, zasoby prywatne domyślnie, alert przy zmianie na publiczne |
| R17 | Aktywne konta byłych pracowników i wykonawców | Wyłączenie kont w dniu odejścia, przegląd co kwartał |
| R18 | Usunięcie danych w chmurze po przejęciu konta, razem z kopią | Kopia niezmienialna w osobnym koncie, alert przy usuwaniu |
| R19 | Przejęcie konta CI/CD i złośliwy kod na stronach klientów | Tokeny z minimalnymi uprawnieniami, zatwierdzanie wdrożeń produkcyjnych |

Dlaczego kopia w **osobnym** koncie: atakujący, który przejmie główne konto chmury, mógłby usunąć dane i kopie jednym ruchem. Osobne konto z innymi poświadczeniami i kopią niezmienialną to rozdziela.

## Urządzenia mobilne

| Obszar | Zasada |
|---|---|
| Urządzenia firmowe | Szyfrowany dysk, blokada ekranu, antywirus lub EDR, brak praw administratora u użytkownika, programy tylko z zatwierdzonej listy |
| Urządzenia prywatne | Tylko poczta i narzędzia SaaS w wydzielonym profilu z możliwością zdalnego wylogowania. Bez dostępu do serwera plików i VPN |
| Praca zdalna i poczta | VPN do zasobów biura, MFA do poczty, brak pracy w publicznym Wi-Fi bez VPN, zakaz przekazywania poczty na prywatne konta |
| Dostęp do danych | Najmniejsze uprawnienia, dane klientów tylko na serwerze lub w chmurze, nie lokalnie |
| Aktualizacje i szyfrowanie | Automatyczne aktualizacje, szyfrowanie dysków i telefonów. Urządzenie bez aktualizacji powyżej 30 dni traci dostęp do poczty i VPN |

**Utrata telefonu lub laptopa.** Pracownik od razu zgłasza ją administratorowi IT. Administrator blokuje i zdalnie wymazuje urządzenie, unieważnia sesje i tokeny, wymusza zmianę haseł i MFA oraz sprawdza logi logowań. Jeśli mogły być na nim dane osobowe i nie ma pewności co do szyfrowania, organizacja zgłasza naruszenie do UODO w 72 godziny (art. 33 RODO), a przy kradzieży także na policję.

Nowe ryzyko: R20 (praca na prywatnych urządzeniach bez kontroli).

## IoT

Przykład: kamera IP w biurze.

| Pytanie | Odpowiedź |
|---|---|
| Komunikacja i sieć | Rejestrator w biurze i czasem chmura producenta. Podłączona do VLAN 30 (IoT), bez dostępu do stacji i serwerów |
| Zarządzanie i aktualizacje | Administrator IT, unikalne hasło. Oprogramowanie sprzętowe sprawdzane co miesiąc, urządzenie bez wsparcia producenta jest wymieniane |
| Skutki przejęcia | Podgląd biura i ekranów, wyciek nagrań, wejście do sieci firmy |

**Separacja.** Firewall blokuje ruch z VLAN 30 do pozostałych sieci. Dozwolone jest tylko zapisywanie nagrań na rejestrator. Panel kamery nie jest dostępny z Internetu, administracja tylko ze stacji administratora lub przez VPN.

Nowe ryzyko: R21 (przestarzałe oprogramowanie IoT).

## Informacje publiczne

Analiza ogólna, bez logowania, skanowania i sprawdzania prawdziwych organizacji.

| Informacja | Wykorzystanie w socjotechnice | Ochrona |
|---|---|---|
| Nazwiska i stanowiska | Wybór osoby do podszycia (Tech Lead, administrator) | Mniej szczegółów, potwierdzanie próśb drugim kanałem |
| Adresy e-mail | Wzór imie.nazwisko@firma pozwala odgadnąć adresy całego zespołu | Adresy rolowe na stronie, SPF, DKIM, DMARC |
| Technologie i klienci (Figma, UXPin, portfolio) | Fałszywe powiadomienie z Figma lub faktura ze zmienionym numerem konta | Szkolenie, potwierdzanie zmiany konta telefonem |
| Zdjęcia biura i media społecznościowe | Widoczne ekrany, karty dostępu, nazwa Wi-Fi | Zasady publikacji, sprawdzanie tła zdjęć |

Nowe ryzyka: R22 i R23.
