---
label: Operator niestandardowy
order: 3
---

# Operator niestandardowy

Ta brama pozwala połączyć sklep z zewnętrznym serwisem zatwierdzonym przez SpaceIs, np. hostingiem przyjmującym płatność z portfela. Operator udostępnia dane integracji, obsługuje płatność na swojej stronie i przekazuje jej wynik do SpaceIs.

## Dostępni operatorzy

Aktualne nazwy zatwierdzonych operatorów i ich domeny są widoczne w informacjach na stronie edycji bramy. Korzystaj z tej listy przy konfiguracji.

Jeżeli wybranego operatora nie ma na liście, skontaktuj się z pomocą SpaceIs. Podaj nazwę serwisu, adres jego strony i link do regulaminu. Samo posiadanie adresu płatności lub klucza API nie oznacza, że integracja jest dostępna.

## Przygotowanie

Przed konfiguracją uzyskaj od operatora:

- pełny adres płatności przypisany do Twojego sklepu;
- sekret integracji ze SpaceIs;
- potwierdzenie, że jego integracja ze SpaceIs jest gotowa do użycia.

!!!
Użyj dokładnego adresu otrzymanego od operatora. Musi on korzystać z HTTPS i należeć do zatwierdzonej domeny. Nie zastępuj go adresem strony głównej serwisu.
!!!

## Konfiguracja bramy

Krok 1. Wybierz licencję i przejdź do **Płatności > Bramy płatności > Nowa brama**.

Krok 2. W polu **Operator** wybierz **Operator niestandardowy**. Wpisz nazwę bramy widoczną dla kupującego oraz prowizję zgodną z warunkami operatora. W polu **Ceny wariantów** możesz wybrać **Skopiuj z:** istniejącej bramy innej niż SMS albo ustawić ceny później. Kliknij **Dodaj bramę**.

Krok 3. W edycji bramy sprawdź listę zatwierdzonych operatorów. W sekcji **Konfiguracja bramy** uzupełnij pola **Adres płatności operatora** i **Sekret (klucz API od operatora)**.

Krok 4. Kliknij **Zapisz zmiany**. Sprawdź ceny sprzedawanych wariantów. Jeżeli ich nie skopiowano, dodaj je ręcznie. Przedziały wariantów obejmą nową bramę automatycznie.

Krok 5. Otwórz produkt lub koszyk. Sprawdź nazwę metody, kwotę oraz odnośnik do regulaminu operatora przed udostępnieniem metody klientom.

Zapisany sekret nie jest ponownie wyświetlany. Przy późniejszej edycji pozostaw jego pole puste, aby zachować dotychczasową wartość. Nowy sekret wpisz tylko wtedy, gdy chcesz go zmienić.

## Obsługa płatności

Po wyborze metody kupujący przechodzi na stronę operatora. SpaceIs otrzymuje od niego wynik płatności. Powrót kupującego do sklepu sam w sobie nie potwierdza wpłaty.

W sprawach rozliczeń, prowizji i zwrotów kontaktuj się z operatorem. Problemy widoczne w panelu SpaceIs sprawdzisz w **Błędy płatności**. Przy zgłoszeniu podaj identyfikator transakcji; nie wysyłaj sekretu integracji.

## Najczęstsze pytania

==- Nie widzę opcji Operator niestandardowy
Sprawdź, czy masz już taką bramę w licencji. Można dodać jedną bramę tego typu; kolejne zmiany wykonujesz przez jej edycję. Opcja jest również ukryta, jeśli nie ma dostępnego zatwierdzonego operatora.
==- Adres płatności nie jest przyjmowany
Sprawdź HTTPS oraz zgodność domeny z listą w panelu. Użyj pełnego adresu przekazanego przez operatora. Jeśli korzysta on z innej domeny, skontaktuj się z pomocą SpaceIs przed konfiguracją.
==- Brama jest zapisana, ale nie widać jej przy zakupie
Sprawdź adres, sekret i ceny wariantów. Operator musi nadal być dostępny na liście zatwierdzonych. W koszyku każdy wariant musi mieć cenę dla tej metody.
==- Rozwijam własny sklep przez API
Pobierz dostępne metody z [API wariantów](/api/variants) i użyj wartości `prices[].method`. Nazwę oraz regulamin operatora odczytaj z `providerData`. Dane konfiguracyjne bramy i jej sekret pozostają w panelu SpaceIs.
===
