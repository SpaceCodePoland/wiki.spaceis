---
label: Koszyk i płatności
order: 2
---

# Koszyk i płatności

Koszyk pozwala kupić kilka wariantów w jednej płatności. Możesz przekierować kupującego do strony SpaceIs albo rozpocząć płatność z własnego formularza. Oba endpointy wymagają [autoryzacji kluczem licencji](/api).

## Pozycje koszyka

| Pole | Wymagane | Opis |
| --- | --- | --- |
| `items` | Tak | Lista od 1 do 20 pozycji. |
| `items[].variantId` | Tak | Identyfikator zwrócony przez [API wariantów](/api/variants). |
| `items[].quantity` | Nie | Liczba sztuk od 1 do 99. Domyślnie `1`. |

Każdy wariant może wystąpić na liście tylko raz. Większą liczbę sztuk zapisz w `quantity`. Wszystkie pozycje muszą należeć do jednej licencji. Łączenie serwerów wymaga włączenia tej możliwości w [ustawieniach koszyka](/payments/cart).

Nie przesyłaj ceny ani sumy zamówienia. SpaceIs wylicza je na podstawie aktualnej oferty i wybranej metody. API koszyka nie obsługuje SMS.

## Link do strony płatności

```http
POST /v4/cart/paymentUrl
```

Oprócz `items` możesz podać opcjonalne pole `nick`, aby uzupełnić nick gracza na stronie płatności. Utworzenie linku nie rozpoczyna płatności u operatora.

```bash
curl --request POST 'https://api.spaceis.pl/v4/cart/paymentUrl' \
  --header "Authorization: Bearer $SPACEIS_API_KEY" \
  --header 'Accept: application/json' \
  --header 'Content-Type: application/json' \
  --data '{
    "nick": "Gracz123",
    "items": [
      {
        "variantId": "44444444-4444-4444-8444-444444444444",
        "quantity": 2
      },
      {
        "variantId": "55555555-5555-4555-8555-555555555555",
        "quantity": 1
      }
    ]
  }'
```

Przy odpowiedzi `200` odczytaj `data.paymentUrl` i przekieruj na ten adres kupującego. Używaj pełnego zwróconego adresu, bez zmiany domeny, ścieżki ani parametrów. Link uwzględnia aktywną własną domenę płatności licencji.

## Płatność z własnego formularza

```http
POST /v4/transaction/cartPayment
```

Ten endpoint rozpoczyna płatność. Oprócz `items` przyjmuje:

| Pole | Wymagane | Opis |
| --- | --- | --- |
| `nick` | Tak | Od 3 do 16 znaków: litery `a-z`, `A-Z`, cyfry i `_`. Pierwszym znakiem może być także kropka. |
| `method` | Tak | Wartość `prices[].method` dostępna dla wszystkich pozycji. |
| `methodParameter` | Tak | E-mail kupującego dla płatności z przekierowaniem lub sześciocyfrowy kod dla BLIK Level 0. |
| `clientIp` | Tak | Adres IPv4 lub IPv6 kupującego, ustalony przez serwer sklepu. |
| `additional` | Nie | Dodatkowa informacja integracji, do 255 znaków, bez średników i nowych linii. |
| `discountCodeId` | Nie | Numeryczny identyfikator kodu z `GET /v4/discount_code/{code}`, nie treść kodu. |

Przykład dla metody `paybylinkTransfer`, jeśli jest skonfigurowana w Twoim sklepie i ma ceny dla obu wariantów:

```bash
curl --request POST 'https://api.spaceis.pl/v4/transaction/cartPayment' \
  --header "Authorization: Bearer $SPACEIS_API_KEY" \
  --header 'Accept: application/json' \
  --header 'Content-Type: application/json' \
  --data '{
    "nick": "Gracz123",
    "method": "paybylinkTransfer",
    "methodParameter": "gracz@example.com",
    "clientIp": "192.0.2.10",
    "items": [
      {
        "variantId": "44444444-4444-4444-8444-444444444444",
        "quantity": 2
      },
      {
        "variantId": "55555555-5555-4555-8555-555555555555",
        "quantity": 1
      }
    ]
  }'
```

Przykładowa odpowiedź dla płatności z przekierowaniem:

```json
{
  "success": true,
  "type": "response",
  "data": {
    "providerId": "przykladowa-platnosc-operatora",
    "redirectUrl": "https://platnosci.example/checkout/przyklad",
    "transactionId": "66666666-6666-4666-8666-666666666666",
    "type": "redirectPayment"
  }
}
```

Zapisz `transactionId` po stronie swojego serwera i powiąż go z zamówieniem. Dla `redirectPayment` skieruj kupującego na `redirectUrl`. Dla BLIK Level 0 odpowiedź ma typ `blik0Payment`; kupujący zatwierdza płatność w aplikacji banku. Status transakcji sprawdzaj przez [API transakcji](/api/transactions).

!!!warning Ponowne rozpoczęcie płatności
Nie ponawiaj automatycznie żądania rozpoczynającego płatność po przekroczeniu czasu oczekiwania lub utracie połączenia. Pierwsze żądanie mogło zostać obsłużone. Jeśli otrzymałeś `transactionId`, sprawdź jego status. Jeśli go nie masz, sprawdź transakcje w panelu lub skontaktuj się z pomocą przed kolejną próbą.
!!!

## Najczęstsze błędy

| Komunikat | Co sprawdzić |
| --- | --- |
| `cart payments are disabled` | Dostępność funkcji koszyka dla usługi. |
| `invalid variant` | Aktualny identyfikator wariantu i zgodność licencji. |
| `cart items must belong to one server` | Serwery pozycji lub ustawienie koszyka obejmującego wiele serwerów. |
| `invalid gateway` | Czy metoda jest skonfigurowana w licencji. |
| `sms payments are not available for carts` | Wybierz metodę inną niż SMS. |
| `daily purchase limit reached for this nick` | Dzienny limit zakupów produktu, z uwzględnieniem liczby sztuk. |

Błędy pól formularza mogą być zwracane w `errors`, np. przy powtórzeniu wariantu lub nieprawidłowej ilości. Nie zastępuj błędu API komunikatem o opłaceniu zamówienia.
