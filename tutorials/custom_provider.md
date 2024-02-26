---
label: Konfiguracja integracji "własny operator płatności".
order: 1
---

## Zasada działania

Własna integracja działa na zasadzie obsługiwania przez Ciebie notyfikacji i generowania płatności.

SpaceIs będzie wysyłać request metodą POST na wskazany przez Ciebie adres z bazowymi parametrami przesłanymi jako JSON:

| Parametr | Typ                        | Opis                                   |
|----------|----------------------------|----------------------------------------|
| action   | Enum(generate,isPaid,test) | Akcja, która jest wywoływana           |
| data     | Obiekt                     | Dane, więcej informacji w danej akcji. |

!!!
SpaceIs będzie również wysyłał nagłówek **X-COMMUNICATION-TOKEN**, który musisz sprawdzać w Twojej integracji. Jeśli
nagłówek będzie niepoprawny, odpowiedz samym kodem HTTP 401.
!!!

Jeśli jakaś akcja nie powiedzie się, użyj kodu HTTP 400, używając podanej odpowiedzi:

```json
{
  "error": "Treść błędu"
}
```

## Generowanie płatności (generate)

Obiekt data będzie zawierać:

| Pole         | Typ        | Opis                                                      |
|--------------|------------|-----------------------------------------------------------|
| id           | UUID       | ID transakcji SpaceIs                                     |
| price        | int        | Kwota płatności (wyrażona w groszach)                     |
| email        | string(64) | E-mail kupującego                                         |
| description  | string(32) | Opis płatności, możesz, ale nie musisz go przesyłać dalej |
| identifier   | string(32) | Identyfikator kupującego, np. nick Minecraft              |
| currencyCode | string(3)  | Waluta (obecnie tylko PLN)                                |

### Twoja odpowiedź musi wyglądać następująco:

#### Kod HTTP 202 (przy pozytywnym wygenerowaniu):

| Pole         | Opis           |
|--------------|----------------|
| redirectType | ENUM(url,form) |

Jeśli redirectType == url to musisz do odpowiedzi dodać:

| Pole        | Opis                                           |
|-------------|------------------------------------------------|
| redirectUrl | URL, pod który zostanie przekierowany kupujący |
| providerId  | ID otrzymane od operatora, może być nullem     |

Jeśli redirectType == form to musisz dodać:

| Pole       | Opis                                                                                                          |
|------------|---------------------------------------------------------------------------------------------------------------|
| formUrl    | URL, pod który zostanie wykonany formularz                                                                    |
| formMethod | Metoda przekierowania (GET/POST)                                                                              |
| formParams | Array składający się z klucza i wartości. Klucz to nazwa parametru, a wartość to wartość dla danego parametru |

Przykładowa odpowiedź redirectType == form:

```json
{
  "redirectType": "form",
  "formUrl": "https://pay.example.com",
  "formMethod": "POST",
  "formParams": {
    "serviceId": 123123123,
    "price": 12.34,
    "currency": "PLN"
  }
}

```

Przykładowa odpowiedź redirectType == url:

```json
{
  "redirectType": "url",
  "providerId": "aabbccdd",
  "redirectUrl": "https://pay.example.com/sdfgsdfggdfs"
}
```

## Notyfikacja / webhook operatora

Po poprawnym obsłużeniu przez Ciebie wiadomości zwrotnej od operatora musisz wysłać zapytanie do naszego API v4,
przesyłając już klucz API do licencji (nie klucz do tej integracji). Więcej informacji
tutaj: https://api.spaceis.pl/#tag/Transakcje/operation/zatwierdzaPatnoOrazWykonujeKomendNaSerwerzeUytekNaWasnOdpowiedzialno

!!!
Pamiętaj, że w tym typie integracji, to Ty odpowiadasz za prawidłową integrację. Nie odpowiadamy za Twoje błędy.
!!!

## Potwierdzenie zmiany statusu przez API (isPaid)

W polu data podane będzie tylko **transactionId** zawierające ID transakcji SpaceIs. W odpowiedzi musisz odpowiedzieć
prostym {“valid”:true} bądź {“valid”:false}, jeśli dana transakcja faktycznie została opłacona, odpowiedź wartością
true. Jeśli nie - false. Dopiero przy odpowiedzi “true”, wykonane zostaną komendy, a transakcja zostanie oznaczona jako
opłacona w SpaceIs.

Odpowiedź musi być przesłana kodem HTTP 200.


## Test integracji (test)

Jest to tylko i wyłącznie testowanie poprawności integracji. 
Jeśli token komunikacji zgadza się, odpowiedź kodem HTTP 200 z body:
```json
{
  "status": "ok"
}
```