---
label: Powiadomienia Discord
order: 1
---

# Powiadomienia Discord

Webhooki zakupowe wysyłają informacje o zakupach do wybranego kanału Discord. Możesz ustawić powiadomienia ogólne lub ograniczyć je do konkretnego serwera, produktu albo wariantu.

## Dodawanie webhooka

Krok 1. Przygotuj adres webhooka kanału Discord, na który mają trafiać powiadomienia.

Krok 2. W panelu SpaceIs wybierz licencję i otwórz **Dodatki > Webhooki > Nowy webhook**.

Krok 3. Wklej adres w polu **Adres webhooka Discord**. Wybierz **Zakres** i, jeśli jest wymagany, odpowiedni serwer, produkt lub wariant.

Krok 4. Ustaw tytuł, kolor i opcjonalną treść wiadomości. Włącz **Aktywny** i kliknij **Zapisz**.

## Własna treść wiadomości

W treści możesz użyć aliasów, które zostaną zastąpione danymi zakupu:

| Alias | Znaczenie |
| --- | --- |
| `{NICK}` | Nick kupującego. |
| `{PRODUCT}` | Nazwa produktu. |
| `{VARIANT}` | Nazwa wariantu. |
| `{AMOUNT}` | Kwota. |
| `{METHOD}` | Metoda płatności. |
| `{TRANSACTION_ID}` | Identyfikator transakcji. |

Przykład:

```text
Gracz {NICK} kupił {PRODUCT}, wariant {VARIANT}.
```

Na liście webhooków możesz wyłączyć wysyłanie, zmienić ustawienia lub usunąć webhook. Przed włączeniem sprawdź, kto ma dostęp do kanału i jakie dane chcesz tam udostępniać. Adresu webhooka nie publikuj, ponieważ pozwala wysyłać wiadomości na ten kanał.
