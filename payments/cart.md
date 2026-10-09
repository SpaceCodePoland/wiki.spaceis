# Koszyk

Koszyk pozwala opłacić kilka produktów jednym zamówieniem. Kupujący wybiera produkty w sklepie, a na stronie płatności sprawdza pozycje, warianty i ilości oraz wybiera metodę płatności.

## Przygotowanie sklepu

Krok 1. Skonfiguruj produkty, warianty i ich ceny. Aby opłacić zamówienie razem, pozycje muszą mieć wspólną dostępną metodę płatności.

Krok 2. Sprawdź, czy Twój szablon obsługuje dodawanie produktów do koszyka. Sama zmiana wyglądu strony płatności nie dodaje koszyka do szablonu sklepu. Integrację własnego szablonu opisuje [API koszyka](/api/cart).

Krok 3. W **Moje licencje > Ustawienia > Dodatkowa konfiguracja** określ, czy koszyk może obejmować produkty z różnych serwerów tej samej licencji.

Krok 4. W **Strona płatności > Skórki i wygląd** ustaw wygląd pozycji i możliwość zmiany liczby sztuk. Sprawdź podgląd oraz linki do dokumentów.

!!!
Koszyk obsługuje do 20 różnych wariantów i od 1 do 99 sztuk każdego wariantu. Wszystkie pozycje muszą należeć do jednej licencji. Płatności SMS nie są obsługiwane przez API płatności koszykowych.
!!!

## Zamówienie i realizacja

SpaceIs oblicza cenę na podstawie wariantów, ilości i obowiązujących rabatów. Dostępne metody płatności zależą od wszystkich pozycji w koszyku. Jeżeli brakuje wspólnej metody, sprawdź konfigurację cen produktów.

Jedna płatność może obejmować produkty realizowane na różnych serwerach. Opłacenie zamówienia nie oznacza jeszcze dostarczenia każdej pozycji. Przy zgłoszeniu problemu sprawdź transakcję oraz połączenie z właściwym serwerem gry.

## Dotychczasowe linki

Linki do pojedynczego produktu nadal działają i wyświetlają koszyk z jedną pozycją. Zakup jednej sztuki pojedynczego wariantu może nadal obsługiwać SMS, jeśli ta metoda jest dostępna dla wybranego wariantu. Własny szablon może zachować dotychczasowy zakup pojedynczego produktu i dodać koszyk jako osobną możliwość.
