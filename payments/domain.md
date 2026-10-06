---
label: Własna domena płatności
order: 5
---

# Własna domena płatności

Możesz udostępnić stronę płatności pod własnym adresem, np. `pay.sklep.example`. Potrzebujesz domeny, do której masz prawa, oraz dostępu do jej rekordów DNS.

## Podłączenie domeny

Krok 1. Wybierz licencję i otwórz **Strona płatności > Własna domena**.

Krok 2. Wpisz samą nazwę hosta, np. `pay.sklep.example`, bez `https://`, ścieżki i numeru portu. Kliknij **Podłącz domenę**.

Krok 3. W panelu dostawcy DNS dodaj rekordy pokazane przez SpaceIs. Skopiuj dokładnie ich typ, nazwę i wartość. Oprócz rekordu CNAME mogą być potrzebne rekordy weryfikacji domeny lub certyfikatu.

Krok 4. Jeżeli korzystasz z Cloudflare, ustaw rekord CNAME jako **DNS only**. Możesz też użyć konfiguratora opisanego poniżej.

Krok 5. Po zapisaniu DNS wróć do SpaceIs i kliknij **Sprawdź status**. Poczekaj na aktywację domeny i certyfikatu HTTPS.

!!!
Publikuj linki do własnej domeny dopiero po uzyskaniu statusu **Aktywna**. Zmiany DNS oraz weryfikacja certyfikatu mogą wymagać czasu.
!!!

## Konfigurator Cloudflare

W panelu możesz zlecić ustawienie rekordu CNAME. Podaj token API Cloudflare z uprawnieniami **Zone > DNS > Edit** i **Zone > Zone > Read**, ograniczonymi do właściwej strefy. Sprawdź pokazaną zmianę i potwierdź jej wykonanie.

Token służy do tej operacji i nie jest zapisywany jako ustawienie licencji. Rekordy dodatkowej weryfikacji nadal dodaj zgodnie z instrukcją w panelu. Ręczne ustawienie DNS pozostaje dostępne bez używania konfiguratora.

## Korzystanie z adresu

Po aktywacji API zwraca adresy płatności z podłączoną domeną. Własny szablon powinien używać pola `paymentUrl` otrzymanego z API, zamiast wpisywać domenę płatności na stałe.

Odłączenie domeny nie wyłącza standardowego adresu płatności SpaceIs. Linki opublikowane wcześniej z własną domeną trzeba jednak zaktualizować w sklepie.

==- Domena nadal czeka na aktywację
Sprawdź komplet rekordów z panelu, ich nazwy i wartości oraz ustawienie DNS only w Cloudflare. Upewnij się, że nie pozostał sprzeczny rekord dla tego samego hosta. Po zmianie ponownie sprawdź status.
==- Przycisk podłączenia domeny jest niedostępny
Panel wyświetla informację, jeśli obsługa własnych domen nie jest dostępna. Możesz nadal korzystać ze standardowego adresu płatności i ustawiać wygląd koszyka. W sprawie dostępności skontaktuj się z pomocą SpaceIs.
===
