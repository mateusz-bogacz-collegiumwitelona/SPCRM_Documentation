# Wymagania Niefunkcjonalne

## 1. Architektura i Interfejs

- System musi być aplikacją webową typu PWA (Progressive Web App) działającą poprawnie na urządzeniach mobilnych (Responsive Web Design).

## 2. Bezpieczeństwo i Prywatność Danych API

- **Maskowanie ID (Tokeny):** W komunikacji API (frontend-backend) zabronione jest ujawnianie wewnętrznych kluczy głównych (Id typu Guid) dla kluczowych encji publicznych. Do identyfikacji klientów, kontaktów, zadań czy firm w adresach URL i payloadach należy używać dedykowanego, bezpiecznego pola `Token`.
- **Soft Delete:** Aplikacja musi implementować mechanizm miękkiego usuwania danych (szczególnie w odniesieniu do użytkowników).

## 3. Precyzja Danych Finansowych

- **Zabezpieczenie przed błędami zaokrągleń:** Wszelkie wartości finansowe (np. wartość transakcji, cena jednostkowa produktu w transakcji, ceny katalogowe) muszą być przechowywane w bazie danych jako liczby całkowite (`long`/`int`) ze stałym mnożnikiem precyzji równym 10 000 (np. 1 PLN zapisane jako 10000).

## 4. Model Danych i Baza Danych

- **Technologia:** Baza danych zrealizowana w PostgreSQL ze wsparciem rozszerzenia PostGIS do obsługi danych przestrzennych. Obsługa relacji i zapytań poprzez Entity Framework Core.
- **Geolokalizacja:** Dokładne koordynaty adresów firm muszą być przechowywane jako typy zmiennoprzecinkowe podwójnej precyzji (`Latitude` i `Longitude` typu `double`).
- **Śledzenie zmian:** Każdy główny wpis w bazie danych (np. użytkownicy, firmy, zadania, produkty) musi automatycznie rejestrować datę utworzenia (`CreatedAt`) oraz modyfikacji (`UpdatedAt`)[cite: 1, 2, 3].

## 5. Integracje i Usługi Zewnętrzne

- **OpenStreetMap i Google Maps:** Integracja frontendu wykorzystująca zgromadzone współrzędne geograficzne (`Latitude`, `Longitude`) w celu wyświetlania wszystkich klientów na mapie oraz nawigacji bezpośrednio do nich.
- **Wydajność:** Redis ma służyć jako warstwa pamięci podręcznej (cache) przyspieszająca dostęp do najczęściej używanych danych.
- **Storage plików:** Usługa Minio jako zewnętrzny magazyn dla załączników i plików.
- **Maile:** Do testowania komunikacji mailowej na środowiskach nieprodukcyjnych musi zostać użyte narzędzie MailPit.
