---
label: Przedziały wariantów
order: 4
---

# Przedziały wariantów

Przedział pozwala przygotować wiele wartości produktu w jednym formularzu, np. pakiety od 10 do 100 monet co 10. Kupujący widzi poszczególne wartości jako osobne warianty.

## Dodawanie przedziału

Krok 1. Wybierz licencję, a następnie przejdź do **Sklep > Serwery**. Otwórz kategorię, produkt i jego warianty.

Krok 2. W sekcji **Przedziały wariantów** kliknij **Nowy przedział**.

Krok 3. Uzupełnij formularz:

| Pole | Przykład | Znaczenie |
| --- | --- | --- |
| Szablon nazwy | `{N} monet` | `{N}` zostanie zastąpione wybraną wartością. |
| Szablon komend | `portfel add {NICK} {N}` | `{NICK}` to nick kupującego, a `{N}` to wartość wariantu. Użyj komendy obsługiwanej przez plugin na swoim serwerze. |
| Od | `10` | Najmniejsza wartość. |
| Do | `100` | Górna granica przedziału. |
| Krok | `10` | Różnica między kolejnymi wartościami. |
| Cena za 1 (PLN) | `0.50` | Cena jednej jednostki przed zniżkami. |

Taki przedział udostępni 10 wariantów: 10, 20, 30 aż do 100 monet. Przy cenie 0,50 zł za jednostkę wariant 20 monet kosztuje 10,00 zł przed zniżkami.

Krok 4. Sprawdź liczbę wariantów i podgląd cen. W razie potrzeby ustaw zniżkę podstawową, progi promocyjne lub wymaganie obecności gracza na serwerze.

Krok 5. Kliknij **Zapisz przedział**, a następnie otwórz produkt w sklepie i sprawdź warianty.

!!!
Przedział może obejmować maksymalnie 10 000 wariantów. Ceny przedziału dotyczą bram innych niż SMS. Do sprzedaży potrzebujesz skonfigurowanej bramy płatności.
!!!

## Wybór na stronie płatności

Przedziały są prezentowane na suwaku. Dla zwykłych wariantów możesz wybrać suwak albo kafelki. Ustawienie produktu ma pierwszeństwo przed domyślnym ustawieniem strony płatności; przy więcej niż 10 wariantach używany jest suwak.

## Własny szablon lub integracja

API zwraca wartości przedziału na liście wariantów produktu. Korzystaj z otrzymanych identyfikatorów i cen. Opis integracji znajdziesz w [Wariantach w API](/api/variants).
