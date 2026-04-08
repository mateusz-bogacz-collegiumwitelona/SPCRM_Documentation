# Wymagania Funkcjonalne

## 1. Moduł Ogólny (Każdy użytkownik)

- Każdy użytkownik ma możliwość zalogowania się i wylogowania z systemu.
- Każdy użytkownik przypisany jest do konkretnej roli (np. Handlowiec, Kierownik, Admin) determinującej jego uprawnienia.

## 2. Moduł Handlowca

### Dashboard i Kalendarz (Zadania)

- Dashboard zawiera kalendarz z nadchodzącymi zadaniami (wyjazdami, spotkaniami)
- Spotkania/Zadania mają zdefiniowany priorytet (Niski, Średni, Wysoki) oraz status (Do zrobienia, W trakcie, Zakończone, Przerwa)
- Zadania mogą być bezpośrednio powiązane z konkretnym kontaktem (osobą) lub konkretną transakcją
- Z poziomu spotkania można wyświetlić dedykowane mu notatki oraz przejść do pełnej historii notatek klienta.

### Baza Klientów i Kontaktów

- Handlowiec widzi listę firm (klientów), która zawiera NIP oraz przypisanego opiekuna
- System obsługuje wiele adresów dla jednej firmy, podzielonych na typy: Siedziba główna (Headquarters), Oddział (Branch), Adres rozliczeniowy (Billing), Adres dostawy (Shipping) itp.
- Profil firmy posiada mapkę z pineską oraz przycisk otwierający Google Maps, wykorzystującą dokładne współrzędne geograficzne (szerokość i długość)
- Handlowiec ma dostęp do listy osób kontaktowych w firmie. Każdy kontakt może mieć wiele szczegółów kontaktowych (np. telefon komórkowy, e-mail służbowy, faks) z wyraźnym oznaczeniem kontaktu głównego (IsPrimary).

### Produkty (Specyfika branży stalowej)

- Handlowiec przegląda bazę produktów podzieloną na kategorie i typy (np. Blachy i płaskowniki -> Blachy gorącowalcowane)
- Każdy produkt zawiera kluczowe dla branży parametry: gatunek stali (SteelGrade), grubość, szerokość, długość, średnicę, wagę oraz jednostkę miary (np. kg, m, szt.)
- Widoczna jest cena jednostkowa oraz aktualny stan magazynowy (StockQuantity).

### Transakcje (Deals)

- Lista transakcji wyświetla wartość, walutę (powiązaną z tabelą walut) i przewidywaną datę zamknięcia.
- Każda transakcja może znajdować się w statusie: ToDo, InProgress, Complete lub Cancelled.
- System automatycznie odejmuje zamówione produkty ze stanu, jeśli transakcja przejdzie w status w trakcie przygotowania.
- Handlowiec może dodać nową transakcję, co wymaga wybrania firmy, waluty oraz dodania produktów do transakcji.
- Podczas dodawania produktów do transakcji handlowiec definiuje ich ilość (w najmniejszej jednostce) oraz ostateczną cenę jednostkową.

### Notatki

- Notatki mogą być tworzone i przypisywane nie tylko do firmy, ale też bezpośrednio do konkretnego kontaktu (osoby) lub transakcji.
- Notatki są sortowane po dacie utworzenia i autorze. Handlowiec może edytować wyłącznie te, które sam utworzył.

### Mailing

- Handlowiec może wysłać masową wiadomość z gotowego szablonu, wybierając klientów, język oraz załączając produkty wraz z wynegocjowanymi cenami.

## 3. Moduł Kierownika

- Kierownik dziedziczy wszystkie uprawnienia przypisane do roli Handlowca.
- Ma dostęp do podsumowania postępów konkretnego pracownika, widząc przypisane do niego transakcje i zadania.
- Widzi liczbę transakcji zakończonych sukcesem z możliwością filtrowania po dacie.

## 4. Moduł Administratora

- Administrator widzi listę użytkowników i zarządza nimi (dodawanie, edycja, blokowanie, soft delete, zmiana ról).
- Zarządza słownikami: kategoriami produktów, typami produktów oraz samą bazą produktów.
- Może dodawać, edytować i usuwać produkty oraz ich kluczowe parametry techniczne.
