# Dokumentacja API

API v4 pozwala połączyć własny sklep ze SpaceIs. W tej sekcji znajdziesz zasady integracji oraz przykłady obsługi wariantów i koszyka. Pełna lista endpointów jest dostępna pod adresem [api.spaceis.pl](https://api.spaceis.pl).

## Adres i autoryzacja

Adres bazowy API:

```text
https://api.spaceis.pl/v4
```

Do żądań używaj klucza API wybranej licencji. Przekazuj go w nagłówku `Authorization`, a nie w adresie URL.

```http
Authorization: Bearer TWOJ_KLUCZ_API
Accept: application/json
```

Przy wysyłaniu JSON dodaj nagłówek `Content-Type: application/json`.

!!!warning Klucz API
Wywołuj API z serwera swojego sklepu. Klucza nie umieszczaj w kodzie JavaScript wysyłanym do przeglądarki, publicznym repozytorium ani logach dostępnych dla klientów. Klucz daje dostęp do danych i operacji wybranej licencji.
!!!

## Pierwsze żądanie

W poniższych przykładach `SPACEIS_API_KEY` oznacza zmienną środowiskową z Twoim kluczem. Identyfikatory, adresy e-mail i dane gracza są przykładowe. Zastąp je danymi ze swojego sklepu.

```bash
curl --request GET 'https://api.spaceis.pl/v4/servers' \
  --header "Authorization: Bearer $SPACEIS_API_KEY" \
  --header 'Accept: application/json'
```

Prawidłowa odpowiedź zawiera dane w polu `data`:

```json
{
  "success": true,
  "type": "response",
  "data": []
}
```

Pusta tablica w tym przykładzie oznacza brak serwerów. Po ich dodaniu otrzymasz listę, z której pobierzesz identyfikatory do kolejnych żądań.

## Sposoby integracji płatności

| Sposób | Zastosowanie |
| --- | --- |
| Link produktu z pola `paymentUrl` | Przekierowanie kupującego do wyboru wariantu i płatności na stronie SpaceIs. |
| `POST /cart/paymentUrl` | Utworzenie linku do koszyka z wybranymi wariantami i ilościami. |
| `POST /transaction/cartPayment` | Rozpoczęcie płatności za koszyk z własnego formularza sklepu. |
| `POST /transaction/variantPayment` | Dotychczasowa płatność za pojedynczy wariant. |

Jeżeli korzystasz ze strony płatności SpaceIs, używaj zwróconego `paymentUrl` bez samodzielnego składania adresu. Dzięki temu link uwzględni również aktywną własną domenę płatności.

## Obsługa odpowiedzi i błędów

Sprawdzaj kod HTTP i treść odpowiedzi. Kod `200` po utworzeniu płatności oznacza przyjęcie żądania, a nie potwierdzenie wpłaty.

| Kod HTTP | Znaczenie |
| --- | --- |
| `200` | Żądanie obsłużone prawidłowo. |
| `400` | Operacja niedostępna lub nie udało się rozpocząć płatności. Szczegóły zawiera odpowiedź. |
| `401` | Brak prawidłowego klucza API. |
| `402` | Licencja nie jest aktywna. |
| `403` | Operacja jest niedozwolona lub funkcja jest wyłączona. |
| `404` | Nie znaleziono zasobu dostępnego dla tej licencji. |
| `409` | Konflikt przy realizacji operacji, np. kod rabatowy nie jest już dostępny. |
| `422` | Nieprawidłowe dane lub niedozwolona zawartość koszyka. |
| `429` | Przekroczono limit żądań lub limit zakupów. |
| `500` | Błąd podczas obsługi żądania. |

Przykładowa odpowiedź błędu:

```json
{
  "success": false,
  "type": "error",
  "message": "invalid variant"
}
```

Błędy walidacji mogą mieć pola `message` i `errors`, bez `success` i `type`. W takiej odpowiedzi klucze `errors` wskazują pola wymagające poprawy, np. `items.0.variantId`.

Przy limicie zapytań uwzględnij nagłówki `X-RateLimit-Limit`, `X-RateLimit-Remaining` i `Retry-At`. Ostatni z nich, zwracany po przekroczeniu limitu, określa liczbę sekund oczekiwania. Nie traktuj każdego kodu `429` jako ograniczenia API: może też oznaczać limit zakupów produktu.

## Dalsze kroki

- [Pobieranie produktów i wariantów](/api/variants)
- [Link do koszyka i rozpoczęcie płatności](/api/cart)
- [Sprawdzanie transakcji](/api/transactions)
