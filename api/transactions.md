# Status transakcji

Status odczytasz na podstawie `transactionId` otrzymanego przy rozpoczęciu płatności. Użyj klucza API tej samej licencji.

```http
GET /v4/transaction/info/{transactionId}
```

```bash
curl --request GET \
  'https://api.spaceis.pl/v4/transaction/info/66666666-6666-4666-8666-666666666666' \
  --header "Authorization: Bearer $SPACEIS_API_KEY" \
  --header 'Accept: application/json'
```

## Status płatności

| `data.status` | Znaczenie |
| --- | --- |
| `pending` | Oczekiwanie na wynik płatności. |
| `paid` | Transakcja opłacona. |
| `fail` | Płatność nieudana. |
| `expired` | Transakcja wygasła. |

Powrót z serwisu operatora, obecność `redirectUrl` lub odpowiedź HTTP `200` nie potwierdzają zapłaty. Odczytaj `data.status` z API.

Status `paid` dotyczy płatności. Nie jest potwierdzeniem, że wszystkie komendy zostały już wykonane na serwerach gry. Realizacja zależy również od ich połączenia ze SpaceIs.

## Dane koszyka

Transakcja koszykowa ma `type: "cart"`, `variantId: null` oraz tablicę `items`. Nie zakładaj, że każda transakcja opisuje jeden wariant.

Przykładowy fragment odpowiedzi, ograniczony do danych koszyka:

```json
{
  "success": true,
  "type": "response",
  "data": {
    "id": "66666666-6666-4666-8666-666666666666",
    "type": "cart",
    "variantId": null,
    "status": "paid",
    "amount": 2500,
    "items": [
      {
        "variantId": "44444444-4444-4444-8444-444444444444",
        "productId": "33333333-3333-4333-8333-333333333333",
        "serverId": "11111111-1111-4111-8111-111111111111",
        "productName": "VIP",
        "variantName": "30 dni",
        "quantity": 2,
        "unitAmount": 750,
        "amount": 1500,
        "usesDiscountCode": false
      },
      {
        "variantId": "55555555-5555-4555-8555-555555555555",
        "productId": "77777777-7777-4777-8777-777777777777",
        "serverId": "11111111-1111-4111-8111-111111111111",
        "productName": "Klucz",
        "variantName": "Epicki",
        "quantity": 1,
        "unitAmount": 1000,
        "amount": 1000,
        "usesDiscountCode": false
      }
    ]
  }
}
```

| Pole pozycji | Znaczenie |
| --- | --- |
| `variantId`, `productId`, `serverId` | Identyfikatory kupionego wariantu, produktu i jego serwera. |
| `productName`, `variantName` | Nazwy pozycji zapisane przy zakupie. |
| `quantity` | Liczba kupionych sztuk. |
| `unitAmount` | Cena jednej sztuki w groszach. |
| `amount` | Kwota całej pozycji w groszach. |
| `usesDiscountCode` | Informacja, czy do pozycji zastosowano kod rabatowy. |

!!! Kwoty
Pola transakcji `amount` i `leftAmount` oraz kwoty pozycji `unitAmount` i `amount` są podawane w groszach. `2500` oznacza 25,00 zł. Ceny zwracane w `prices[].amount` przy pobieraniu wariantów są natomiast podawane w PLN.
!!!

Przy koszyku obejmującym wiele serwerów korzystaj z `items[].serverId`. Główne pole `serverId` nie opisuje wszystkich pozycji takiego zamówienia.

## Udostępnianie statusu kupującemu

Pobieraj dane transakcji na swoim serwerze i sprawdzaj, czy należą do zamówienia danego klienta. Do przeglądarki przekazuj tylko potrzebne informacje. Nie udostępniaj pełnej odpowiedzi API jako publicznego podglądu: może zawierać dane kupującego, np. nick i parametr użyty przy płatności.

Sprawdzaj status w odstępach uwzględniających [limity API](/api). Po otrzymaniu końcowego wyniku zakończ odpytywanie. Odświeżanie statusu nie wymaga ponownego rozpoczynania płatności.
