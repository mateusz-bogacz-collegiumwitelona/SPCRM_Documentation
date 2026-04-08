# PRD: Simply Poor CRM - prosty crm do zarządzania kontaktami w firmie handlowej

- **Autor:** Mateusz Bogacz-Drewniak
- **Data:** 02.02.2026
- **Status:** Szkic

---

## 1. Podsumowanie

CRM (Customer Relationship Management) do zarządzania relacjami w firmie handlującej stalą. Ma na celu ułatawić zarządanie relacjami firma-klient w obszarze handlu stalą/wyrobami stalowymi.

---

## 2. Opis Problemu

### Jaki problem rozwiązujemy?

Bazując na doświadczeniach nabytych w pracy jak szeroko pojęty HelpDesk zauważyłem że wiele firm kożysta z starych, niespełniających obecych wymagań CRM. Głównie chodzi o dostępność, gdyż np. handlowiec musi po powrocie do firmy uzupełnić dane z wyjazdu, bądź musi się z laptopa łączyć przez VPN do sieci firmowej i w biegu uzupełniać dane.

### Dla kogo jest ten produkt?

- **Główna persona:** Anna, Handlowiec
- **Poboczne persony:** Marek, dyrektor ds. handlu

---

## 3. Cele i Mierniki Sukcesu

### Cele projektu

- **Cel 1:** Ułatwienie dostępu do danych klienta poza firmą

---

## 4. Wymagania i Zakres

### Kluczowe historyjki użytkownika

- **US-001:** Jako handlowiec chce mieć łatwy dostęp do notatke i kontaktów klientów
- **US-002:** Jako dyrektor ds. handlu chce mieć wgląd w postępy pracowników

### Zakres projektu

**Co jest w zakresie (In Scope):**

- Tworzenie i edycja notatek.
- Wyszukiwarka pełnotekstowa.
- Możliwość podglądu danych klienta
- Możliwość szybkiego nawigowania do klienta
- Możliwość edycji danych klienta
  ...

**Co jest poza zakresem (Out of Scope):**

- Natywna aplikacja mobilna (Android/iOS) – system będzie aplikacją webową (PWA/RWD).

- Zaawansowany edytor szablonów mailowych HTML (będą używane proste, predefiniowane szablony tekstowe).

- Integracja z zewnętrznymi systemami ERP/FK w czasie rzeczywistym (zakładamy import/eksport danych lub ręczną synchronizację na potrzeby MVP).

---

## 5. Doświadczenie Użytkownika (UX) i Projekt Interfejsu (UI)

- **Link do projektu w Figmie:** [https://www.figma.com/design/rtTK2pnm0Mw4znDZq1A0rx/In%C5%BCynierka--Copy-?node-id=0-1&m=dev](https://www.figma.com/design/rtTK2pnm0Mw4znDZq1A0rx/In%C5%BCynierka--Copy-?node-id=0-1&m=dev)

---

## 6. Kwestie Techniczne (opcjonalnie)

- **Stack technologiczny:**
  - [+] Backend: .NET 9 / EF CORE
  - [+] Frontend: React route
  - [+] Baza danych: PostgreSQL + PostGIS
  - [+] Cache: Redis
  - [+] Trzymanie plików: Minio
  - [+] Testowe maile: MailPit

- **Integracje:**
  - [+] OpenStreetMap (pineski i mapa ze wszystkimi klientami. różne kolory - różny stan klienta )
  - [+] GoogleMap (możliwość kliknięca w przycisk żeby włączyć nawigacje)
