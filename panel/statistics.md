---
label: Transakcje i statystyki
order: 2
---

# Transakcje i statystyki

Dane dotyczą licencji wybranej w menu. Dostęp do transakcji i statystyk może być ograniczony przez uprawnienia subkonta.

## Transakcje koszykowe

W zestawieniu transakcji koszyk jest jednym zamówieniem. Otwórz jego szczegóły, aby zobaczyć produkty, warianty, liczbę sztuk i wartości pozycji. Przy zgłoszeniu problemu posługuj się identyfikatorem transakcji.

Status płatności i wykonanie komend na serwerze gry to osobne informacje. Jeżeli opłacony produkt nie dotarł do gracza, sprawdź serwer wskazany przy tej pozycji oraz jego połączenie ze SpaceIs.

## Eksport CSV

W zestawieniu transakcji ustaw potrzebne filtry i wybierz eksport CSV. Eksport uwzględnia wybrane filtry.

Koszyk jest rozpisany na osobne wiersze, po jednym dla każdej pozycji. Wspólny identyfikator transakcji pozwala połączyć je w jedno zamówienie.

| Kolumna | Znaczenie |
| --- | --- |
| Kwota | Wartość całej transakcji, zapisana tylko w pierwszym wierszu zamówienia. |
| Kwota po prowizji | Wartość całej transakcji po prowizji, również tylko w pierwszym wierszu. |
| Pozycja | Numer pozycji w zamówieniu. |
| Ilość | Liczba sztuk danego wariantu. |
| Cena za sztukę | Cena jednostkowa. |
| Wartość pozycji | Łączna wartość danego wiersza. |
| Wartość pozycji po prowizji | Kwota przypisana do pozycji po prowizji. |

Kwoty w CSV są zapisane w PLN. Nie dodawaj wartości całej transakcji do wartości jej pozycji, ponieważ oznaczałoby to dwukrotne policzenie tego samego zakupu.

## Statystyki

W sekcji **Statystyki** wybierz interesujące zestawienie i serwer. Sprawdzaj okres podany przy wykresie lub w filtrach: część podsumowań obejmuje ostatnie 24 godziny, 30 dni lub 12 miesięcy.

Zakupy koszykowe są uwzględniane w zestawieniach produktów i serwerów według pozycji zamówienia. Liczba sprzedanych sztuk może być większa od liczby transakcji, gdy kupujący zamawia kilka produktów lub sztuk jednocześnie.
