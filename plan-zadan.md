# Plan Zadań

## Faza 1: Projektowanie interfejsu i UX

- Stworzenie makiet aplikacji w Figmie uwzględniających interfejs responsywny (RWD).
- Zaprojektowanie kluczowych widoków: dashboard z kalendarzem, lista klientów, profil klienta z mapą, moduł transakcji oraz panel administratora.

## Faza 2: Konfiguracja infrastruktury i środowiska

- Konfiguracja środowiska z wykorzystaniem PostgreSQL z PostGIS, Redis, Minio, MailPit.
- Inicjalizacja projektu backendowego w technologii .NET 9 z wykorzystaniem Entity Framework Core.
- Inicjalizacja projektu frontendowego w React z routingiem, przygotowanego jako aplikacja webowa.

## Faza 3: Baza danych i fundamenty API

- Implementacja modeli bazy danych na podstawie diagramu ERD, obejmująca m.in. użytkowników, firmy, adresy, kontakty, transakcje, notatki i produkty.
- Implementacja mechanizmów logowania i wylogowywania.
- Wdrożenie autoryzacji opartej na rolach: Handlowiec, Kierownik, Admin.
- Implementacja w API tokenów zamiast publicznego ujawniania wewnętrznych identyfikatorów (Id).

## Faza 4: Panel Administratora i zarządzanie słownikami

- Budowa listy użytkowników dla administratora z opcjami dodawania, edycji, blokowania, odblokowywania i usuwania (soft delete).
- Możliwość nadawania nowych ról użytkownikom przez administratora.
- Stworzenie modułu do zarządzania bazą produktów, kategoriami oraz typami.

## Faza 5: Kluczowe moduły CRM (Klienci, Kontakty, Notatki)

- Wdrożenie listy klientów z opcją wyszukiwania po nazwie i NIP oraz sortowania po nazwie i dacie ostatniej transakcji.
- Stworzenie profilu klienta wyświetlającego jego dane, przypisanego opiekuna oraz stan zadłużenia w zależności od waluty.
- Budowa modułu notatek z możliwością dodawania, sortowania (po dacie i autorze) oraz edytowania wyłącznie własnych wpisów.

## Faza 6: Moduł Handlowy (Transakcje i Mapa)

- Implementacja obsługi transakcji uwzględniająca kwoty, waluty, statusy (ToDo, InProgress, Complete, Break) oraz priorytety.
- Automatyczne odejmowanie produktów z listy zamówień, gdy transakcja jest w trakcie przygotowania.
- Zastosowanie mnożnika 10 000 dla wartości transakcji i cen jednostkowych w celu zachowania precyzji.
- Integracja OpenStreetMap do oznaczania klientów na mapie pineskami oraz przycisku Google Maps do nawigacji.

## Faza 7: Funkcje zaawansowane (Mailing, Dashboard, Szukanie)

- Budowa dashboardu dla handlowca z kalendarzem nadchodzących wyjazdów i spotkań.
- Wdrożenie mailingu umożliwiającego wysyłkę z predefiniowanych szablonów tekstowych do wybranych klientów z opcją wyboru języka (PL/ENG).
- Wykorzystanie narzędzia MailPit do testowania wysyłki maili.
- Stworzenie widoku dla kierownika prezentującego listę pracowników, ich transakcje i wskaźnik sukcesu.
- Zintegrowanie wyszukiwarki pełnotekstowej opartej na ElasticSearch.

## Faza 8: Finalizacja i optymalizacja

- Wdrożenie cache'owania danych za pomocą Redis.
- Skonfigurowanie usługi Minio do przechowywania plików.
- Dodanie formularza umożliwiającego zgłaszanie problemów technicznych przez wszystkich użytkowników.
- Testy całego systemu i wprowadzanie poprawek.
