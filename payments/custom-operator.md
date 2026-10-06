---
label: Operator niestandardowy
order: 3
---

# Operator niestandardowy

Ta brama pozwala korzystać z operatora zatwierdzonego przez SpaceIs. Operator udostępnia dane potrzebne do połączenia Twojego sklepu i obsługuje płatność na swojej stronie.

## Przygotowanie

Przed konfiguracją uzyskaj od operatora:

- adres płatności przypisany do Twojego sklepu;
- sekret integracji;
- potwierdzenie, że jego integracja ze SpaceIs jest gotowa do użycia.

!!!
Nie podłączysz w ten sposób dowolnego adresu. Operator i jego domena muszą być zatwierdzeni przez SpaceIs. Jeżeli operatora nie ma na liście, skontaktuj się z pomocą przed rozpoczęciem konfiguracji.
!!!

## Konfiguracja bramy

Krok 1. Wybierz licencję i przejdź do **Płatności > Bramy płatności > Nowa brama**.

Krok 2. Wybierz **Operator niestandardowy**, wpisz nazwę bramy i prowizję operatora, a następnie kliknij **Dodaj bramę**.

Krok 3. W edycji bramy sprawdź listę zatwierdzonych operatorów. W sekcji **Konfiguracja bramy** wpisz adres płatności operatora i otrzymany sekret. Adres musi używać `https://` i należeć do zatwierdzonej domeny. Nazwa bramy będzie widoczna dla kupującego.

Krok 4. Zapisz bramę i przypisz jej ceny do sprzedawanych wariantów.

Krok 5. Otwórz produkt lub koszyk. Sprawdź nazwę metody, kwotę oraz odnośnik do regulaminu operatora przed udostępnieniem metody klientom.

## Obsługa płatności

Po wyborze metody kupujący przechodzi na stronę operatora. SpaceIs otrzymuje od niego wynik płatności. Powrót kupującego do sklepu sam w sobie nie potwierdza wpłaty.

W sprawach rozliczeń, prowizji i zwrotów kontaktuj się z operatorem. Problemy widoczne w panelu SpaceIs sprawdzisz w **Błędy płatności**. Przy zgłoszeniu podaj identyfikator transakcji; nie wysyłaj sekretu integracji.
