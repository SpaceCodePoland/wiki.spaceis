---
label: Produkty i warianty
order: 3
---

# Produkty i warianty

Każdy wariant ma własny identyfikator i listę dostępnych cen. Dotyczy to również wartości utworzonych przez [przedział wariantów](/panel/variants).

## Pobieranie oferty

Krok 1. Pobierz serwery przez `GET /v4/servers`.

Krok 2. Pobierz serwer przez `GET /v4/server/{param}`. W miejscu `param` podaj identyfikator lub slug serwera. W `data.categories` znajdziesz kategorie i ich produkty. Każdy produkt zawiera również `paymentUrl`, czyli link do strony płatności.

Krok 3. Pobierz warianty produktu:

```http
GET /v4/server/{param}/category/{categoryId}/product/{productId}/variants
```

Wszystkie identyfikatory pobierz z odpowiedzi dla tej samej licencji. Żądanie wymaga [nagłówka autoryzacji](/api).

## Dane wariantu

Odpowiedź zawiera `data.product` oraz tablicę `data.variants`.

| Pole wariantu | Znaczenie |
| --- | --- |
| `id` | Identyfikator przekazywany jako `variantId` przy zakupie. |
| `name` | Nazwa wyświetlana kupującemu. |
| `prices` | Dostępne ceny i metody płatności. |

| Pole w `prices` | Znaczenie |
| --- | --- |
| `amount` | Cena w PLN, np. `10.50` oznacza 10,50 zł. |
| `name` | Nazwa bramy wyświetlana kupującemu. |
| `method` | Identyfikator metody przekazywany do rozpoczęcia płatności. |
| `type` | Typ metody, np. `transfer` lub `sms`. |
| `sms` | Informacja, czy jest to SMS, oraz numer i treść wiadomości. |
| `providerData` | Nazwa operatora i adresy jego strony, regulaminu, reklamacji oraz obrazu. |

Nie zastępuj `method` nazwą z pola `name`. Nie zakładaj też, że wszystkie warianty mają te same metody lub ceny. W koszyku użyj metody dostępnej dla każdej pozycji. SMS nie jest obsługiwany przez API koszyka.

## Przedziały wariantów

Przedział jest widoczny w API jako lista osobnych wariantów. Przykładowo wartości 10, 20 i 30 monet otrzymują oddzielne identyfikatory, nazwy i ceny. Sklep wybiera konkretny wariant tak samo jak przy zwykłej liście produktów.

!!!warning Format identyfikatora
Traktuj `id` jako nieprzezroczysty ciąg znaków. Nie wymagaj formatu UUID, nie rozdzielaj identyfikatora na części i nie twórz go samodzielnie. Przekaż dokładnie wartość zwróconą przez API.
!!!

`quantity` w koszyku oznacza liczbę sztuk wybranego wariantu. Jeżeli wariant zawiera 20 monet, `quantity: 2` oznacza dwa takie pakiety, czyli łącznie 40 monet.

## Zgodność istniejącego sklepu

Dotychczasowy endpoint `POST /v4/transaction/variantPayment` nadal służy do zakupu pojedynczego wariantu. Obsługa przedziałów nie wymaga przejścia na koszyk.

Przed udostępnieniem przedziałów sprawdź, czy szablon:

- pobiera warianty i metody z API;
- przekazuje identyfikatory bez zmian i nie ogranicza ich do UUID;
- wyświetla większą liczbę opcji w czytelny sposób;
- obsługuje brak ceny lub niedostępność wybranej metody;
- rozróżnia kwoty oferty w PLN od [kwot transakcji w groszach](/api/transactions).

Po zmianie oferty w panelu odśwież dane pobierane przez swój sklep. Ostateczna kwota zakupu jest wyliczana przez SpaceIs przy rozpoczęciu płatności.
