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

## Ręczna konfiguracja DNS

Token API nie jest potrzebny do ręcznej konfiguracji. W zakładce **Własna domena** znajdziesz rekord CNAME z adresem docelowym przypisanym do Twojej licencji. Skopiuj całą wartość z pola **Wartość / Target**, bez `https://` i bez ścieżki. Nazwa pokazana przed podłączeniem domeny jest tylko przykładem.

Krok 1. Otwórz panel dostawcy DNS swojej domeny. W Cloudflare wybierz domenę, następnie **DNS / Records / Add record**.

Krok 2. Dodaj rekord CNAME. Dla przykładowego adresu `pay.sklep.example` ustaw:

| Pole | Wartość |
| --- | --- |
| Typ / Type | `CNAME` |
| Nazwa / Name | `pay`, jeśli edytujesz strefę `sklep.example` i dostawca dopisuje domenę automatycznie. W przeciwnym razie pełne `pay.sklep.example`. |
| Wartość / Target | Dokładny adres z pola **Wartość / Target** w panelu SpaceIs dla tej licencji. |
| Proxy status w Cloudflare | **DNS only**, szara chmurka. |
| TTL | **Auto** w Cloudflare lub domyślna wartość u innego dostawcy. |

Krok 3. Jeśli panel SpaceIs wyświetla dodatkowe rekordy TXT lub CNAME, dodaj je osobno. Skopiuj ich dokładne nazwy i wartości. Służą do potwierdzenia własności domeny lub wystawienia certyfikatu HTTPS.

Krok 4. Zapisz rekordy i wróć do SpaceIs. Kliknij **Sprawdź status DNS i SSL**. Udostępnij nowy adres klientom, gdy domena i certyfikat będą aktywne.

!!!
CNAME nie może współistnieć z rekordem A, AAAA ani innym rekordem dla tej samej nazwy. Jeśli wybrany adres jest już używany, wybierz inną subdomenę do płatności.
!!!

Sposób dodawania rekordów opisuje również [instrukcja Cloudflare](https://developers.cloudflare.com/dns/manage-dns-records/how-to/create-dns-records/).

## Konfigurator Cloudflare

Konfigurator jest opcjonalny. Jeśli rekord został już dodany ręcznie, wystarczy sprawdzić status DNS i SSL.

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
