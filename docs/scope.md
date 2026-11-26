# Zakres projektu

Projekt obejmuje bezpieczeństwo infrastruktury informatycznej Witchak Modeling: ludzi, urządzenia, systemy i dane, z których firma korzysta przy tworzeniu i utrzymywaniu stron internetowych klientów.

## Co obejmuje

| Obszar | Elementy |
|---|---|
| Dane | Dane klientów, kod źródłowy, dokumentacja projektowa, dane produkcyjne stron |
| Systemy | CRM, serwer plików, poczta elektroniczna, bazy danych, GitHub, hosting stron |
| Infrastruktura | Laptopy pracowników, serwery w biurze, sieć LAN i Wi-Fi, usługi chmurowe, urządzenia mobilne, IoT (kamera, drukarka) |
| Procesy | Praca zdalna, wdrażanie stron (CI/CD), kopie zapasowe, korzystanie z AI, reagowanie na incydenty |

## Czego nie obejmuje

- Bezpieczeństwa infrastruktury samych dostawców chmury i SaaS. Oceniamy tylko to, jak firma z nich korzysta i jak je konfiguruje.
- Bezpieczeństwa fizycznego budynku poza urządzeniami IT w biurze.
- Testów na prawdziwych systemach. Projekt jest analizą i projektem zabezpieczeń.

## Przyjęte założenia

Dane z rejestru aktywów nie opisują wszystkiego, więc przyjęliśmy założenia typowe dla firmy tej wielkości:

1. Jedno biuro, bez oddziałów. Pracownicy zdalni łączą się przez VPN.
2. IoT w biurze to drukarka sieciowa i kamera IP.
3. Produkcyjne strony klientów i ich bazy działają w chmurze hostingowej. W biurze stoją serwery testowe, systemy wewnętrzne i serwer plików.
4. Kod jest w GitHub, a CRM, poczta i zarządzanie projektami to usługi SaaS.
5. Kopie zapasowe: serwer kopii w biurze i kopia zewnętrzna w chmurze. To stan docelowy, bo z analizy zagrożeń wynika, że dziś firma nie ma aktualnego backupu.

## Główne zagrożenia, od których zaczęliśmy

| Zagrożenie | Skutek |
|---|---|
| Phishing | Wyciek danych osobowych, przejęcie kont |
| Działanie nieuczciwego pracownika | Kradzież danych poufnych i kodu |
| Wyciek danych | Spadek reputacji, kary z RODO |
| Awaria infrastruktury | Brak dostępności usług, utrata danych |
| Błędna konfiguracja usługi chmurowej | Podatność na atak, dostęp osób trzecich |
| Przejęcie konta administratora | Nieautoryzowane zmiany w całej infrastrukturze |
