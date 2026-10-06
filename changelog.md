---
icon: clock
---

# Changelog

Historia funkcji i poprawek SpaceIs. Wpisy historyczne opisują stan z chwili danego wydania. Aktualną dostępność integracji sprawdzisz na stronie [operatorów płatności](/payments/providers).

## Następna aktualizacja

Zmiany przygotowane do kolejnego wydania. Data udostępnienia zostanie podana przy publikacji aktualizacji.

### Koszyk i strona płatności

1. Dodano [koszyk](/payments/cart) pozwalający opłacić kilka produktów i sztuk jednym zamówieniem.
2. Dodano możliwość łączenia produktów z różnych serwerów tej samej licencji, jeśli właściciel włączy tę opcję.
3. Rozszerzono podsumowanie zamówienia o pozycje, warianty, ilości i wartości produktów. Dostępne metody płatności uwzględniają wszystkie pozycje koszyka.
4. Dodano dziewięć skórek strony płatności: Luna, Nova, Orbit, Aurora, Forma, Atelier, Signal, Slate i Noir.
5. Dodano [ustawienia wyglądu](/payments/checkout): palety kolorów, logo, teksty i widoczność elementów oraz podgląd roboczy przed zapisaniem zmian.
6. Dodano wybór między kafelkami a suwakiem dla zwykłych wariantów. Ustawienie można zmienić osobno dla produktu.
7. Odświeżono strony statusu płatności oraz podsumowanie zamówienia. Zachowano możliwość powrotu do strony statusu obsługiwanej przez szablon sklepu.
8. Dotychczasowe linki do pojedynczych produktów otwierają stronę płatności z jedną pozycją. Dodanie koszyka do własnego szablonu wymaga jego osobnej integracji.
9. Usunięto zapamiętywanie nicku i adresu e-mail kupującego na stronie płatności.

### Domeny i dokumenty sklepu

1. Dodano [własne domeny płatności](/payments/domain), instrukcje DNS oraz podgląd stanu domeny i certyfikatu HTTPS.
2. Dodano opcjonalny konfigurator rekordu DNS dla domen obsługiwanych przez Cloudflare.
3. Dodano osobne pola na linki do regulaminu i polityki prywatności sklepu.

### Transakcje, statystyki i API

1. Dodano [API koszyka](/api/cart): tworzenie linku do strony płatności i rozpoczynanie płatności za wiele pozycji.
2. Rozszerzono [informacje o transakcji](/api/transactions) o pozycje koszyka, ilości oraz ceny jednostkowe i wartości pozycji.
3. Uwzględniono koszyki w [statystykach, zestawieniu transakcji i eksporcie CSV](/panel/statistics), a także w rankingach produktów i kupujących.
4. Dostosowano powiadomienia e-mail, webhooki Discord i widgety OBS do zakupów koszykowych.
5. Dodano realizację pozycji koszyka na właściwych serwerach. Problem z jednym serwerem nie zatrzymuje realizacji pozostałych pozycji.
6. Poprawiono obsługę rabatów procentowych z częścią dziesiętną oraz zakupów o wartości 0 zł po zastosowaniu kodu rabatowego.
7. Usprawniono odświeżanie statusu transakcji po zmianie jej stanu.
8. Zachowano dotychczasowy sposób zakupu pojedynczych wariantów przez API. Linki `paymentUrl` uwzględniają aktywną własną domenę płatności.

### Panel i zgodność

1. Oznaczono nowe opcje strony płatności znacznikiem **BETA** i uzupełniono ich tłumaczenia.
2. Usunięto stary panel. Zarządzanie sklepem odbywa się w nowym [panelu SpaceIs](/panel).
3. Usunięto dawną usługę hostowania sklepów w SpaceIs (SaaS). Szablony instalowane na własnym hostingu nadal korzystają z API SpaceIs.
4. Uzupełniono Wiki o instrukcje panelu, koszyka, domen, wariantów i API. Zaktualizowano listę operatorów oraz usunięto nieaktualny poradnik porównawczy.

## Zmiany po v4.0.21

Zbiorcze uzupełnienie historii zmian w panelu, sklepie i integracjach płatności.

### Panel i nawigacja

1. Wprowadzono nowy [panel zarządzania](/panel) z jasnym i ciemnym motywem oraz układem dostosowanym do telefonów.
2. Odświeżono karty licencji, serwerów, kategorii, produktów i wariantów, a także portfel, szablony i zgłoszenia pomocy.
3. Ujednolicono formularze, komunikaty walidacji, przyciski i widoki bez danych. Poprawiono czytelność tabel na mniejszych ekranach.
4. Dodano wybór bieżącej licencji, rozbudowano wyszukiwanie i uporządkowano menu.
5. Rozbudowano kokpit o podsumowania sprzedaży, ostatnie zakupy, najlepsze produkty i metody płatności.
6. Dodano centrum powiadomień o sprzedaży, błędach płatności i zbliżającym się końcu licencji.
7. Uzupełniono polskie i angielskie tłumaczenia oraz poprawiono wyświetlanie dat, kwot i liczb.
8. Poprawiono zmianę kolejności elementów katalogu oraz wygląd stron błędów i przerwy technicznej.

### Konto i dostęp do sklepu

1. Dodano [logowanie i łączenie kont z Google oraz Discordem](/panel/account).
2. Połączenie z istniejącym kontem wymaga zalogowania do SpaceIs i potwierdzenia w ustawieniach. Zgodny adres e-mail nie łączy kont automatycznie.
3. Rozszerzono weryfikację dwuetapową o kody e-mail oraz klucze sprzętowe i passkeys. Logowanie przez Google lub Discord nadal uwzględnia włączone 2FA.
4. Uproszczono rejestrację, odświeżono logowanie i odzyskiwanie hasła oraz poprawiono konfigurację metod 2FA.
5. Uporządkowano uprawnienia subkont oraz dostęp do danych wybranej licencji.
6. Dodano dziennik zmian licencji, pozwalający właścicielowi przeglądać działania wykonane w sklepie.
7. Poprawiono obsługę anulowanego lub wygasłego logowania przez Google i Discord.

### Produkty, warianty i promocje

1. Dodano [przedziały wariantów](/panel/variants) z początkiem, końcem, krokiem, ceną jednostkową oraz szablonami nazwy i komend.
2. Dodano zniżkę podstawową, progi promocyjne i podgląd cen dla przedziałów. Poszczególne wartości są dostępne w sklepie i API jako osobne warianty.
3. Zachowano publiczne identyfikatory UUID wariantów przedziałowych oraz możliwość zakupu przez dotychczasowe integracje.
4. Dodano masową zmianę cen wariantów produktu oraz kopiowanie cen z istniejącej bramy przy dodawaniu nowej.
5. Dodano promocje z datą rozpoczęcia i zakończenia.
6. Dodano limity użyć i termin ważności kodów rabatowych.
7. Dodano dzienne limity zakupów produktu dla gracza oraz podgląd sklepu z panelu.
8. Dodano możliwość czasowego blokowania nicków i adresów e-mail na czarnej liście.

### Statystyki i powiadomienia

1. Rozbudowano statystyki o przegląd sprzedaży, zestawienia produktów, metod płatności i klientów oraz filtrowanie według serwera i okresu.
2. Odświeżono wykresy, legendy i podpowiedzi z wartościami w jasnym i ciemnym motywie.
3. Dodano mapę aktywności zakupów według dnia tygodnia i godziny oraz lejek pokazujący wejścia na stronę płatności, rozpoczęte płatności i opłacone transakcje.
4. Rozbudowano podgląd transakcji i eksport CSV. Poprawiono wcześniejsze eksporty transakcji do arkusza.
5. Dodano opcjonalny codzienny raport sprzedaży wysyłany e-mailem.
6. Dodano osobną sekcję [webhooków Discord](/panel/webhooks) dla całej licencji, serwera, produktu lub wariantu, z własną treścią, tytułem i kolorem powiadomienia.
7. Dodano możliwość włączania i wyłączania webhooków z listy oraz wybór celu powiadomień w formularzu.
8. Ujednolicono wygląd wiadomości systemowych i dodano e-mailowe potwierdzenia zakupu licencji oraz szablonów.

### Operatorzy płatności i portfel

1. Dodano integracje Paymentic dla płatności online, paysafecard i Direct Carrier Billing.
2. Dodano tryb testowy Paymentic oraz opcję ukrycia paysafecard na jego stronie płatności online.
3. Dodano integrację płatności ChunkServe.pl.
4. Dodano [operatora niestandardowego](/payments/custom-operator). Dostępne są wyłącznie integracje i domeny zatwierdzone przez SpaceIs.
5. Zaktualizowano możliwość dodawania starszych bram. Aktualną listę nowych i starszych integracji opisano w [dostępnych operatorach](/payments/providers).
6. Doładowania portfela SpaceIs oparto wyłącznie na Paymentic. Dotyczy to portfela właściciela konta, a nie listy metod płatności w jego sklepie.
7. Poprawiono obsługę potwierdzeń płatności, kwot i komunikatów błędów w integracjach operatorów, w tym Paymentic, CashBill BLIK, SkillHost, HotPay i DPay.
8. Poprawiono rozliczanie powtórzonych potwierdzeń operatorów, aby zakup lub doładowanie portfela nie były naliczane ponownie.
9. Poprawiono obsługę płatności o wartości 0 zł po rabacie oraz sytuacji, gdy na stronie płatności nie ma dostępnych metod.

### API, plugin i niezawodność

1. Zachowano obsługę dotychczasowych zakupów pojedynczych wariantów oraz zgodny format oferty w API v4.
2. Zakończono obsługę starego pluginu korzystającego z API v3. Do połączenia serwera gry należy używać aktualnego [pluginu SpaceIs](/plugin) z API v4.
3. Poprawiono uwzględnianie promocji, kodów rabatowych i limitów zakupów w API.
4. Usprawniono obsługę błędów dostarczania zakupów na serwer gry.
5. Ujednolicono sprawdzanie dostępu do panelu, licencji i funkcji subkont oraz ochronę danych zwracanych przez API.

## v4.0.21

#### 22.12.2023

1. Dodano płatności paysafecard i PayPal przez SimPay.pl.
2. Usunięto pole „Klucz API” z konfiguracji operatora SimPay.

## v4.0.20

#### 15.12.2023

1. Dodano nowy styl strony płatności pay.spaceis.pl.
2. Ujednolicono opisy transakcji wysyłane do operatorów płatności.

## v4.0.19

#### 12.12.2023

1. Przebudowano zarządzanie licencją, aby uporządkować ustawienia i ułatwić ich konfigurację.

## v4.0.18

#### 10.12.2023

1. Dodano operatora płatności ZEN.

## v4.0.17

#### 27.11.2023

1. Dodano operatora płatności TostHost.pl.

## v4.0.16

#### 27.10.2023

1. Zaktualizowano informacje o DotPay zgodnie z informacjami Przelewy24.

## v4.0.15

#### 14.10.2023

1. Dodano obsługę przelewów SimPay.pl.

## v4.0.14

#### 31.08.2023

1. Dodano generowanie kodów voucherów przez API z miesięcznym okresem ważności.

## v4.0.13

#### 25.07.2023

1. Uzupełniono konfigurację weryfikacji dwuetapowej o klucz do ręcznego dodania konta w aplikacji uwierzytelniającej.
2. Po zmianie hasła pozostałe zalogowane sesje są automatycznie wylogowywane.
3. Dodano aliasy komend `{DISCOUNT_CODE}` i `{DISCOUNT_CODE_PERCENTAGE}`. Pierwszy zawiera użyty kod rabatowy lub `NONE`, a drugi wartość procentową rabatu.

## v4.0.12

#### 23.07.2023

1. Dodano bezpośrednią integrację paysafecard.

## v4.0.11

#### 16.07.2023

1. Dodano operatora płatności SkillHost.pl.

## v4.0.10

#### 10.07.2023

1. Dodano możliwość ponownego wykonania komend dla opłaconej transakcji.

## v4.0.9

#### 27.06.2023

1. Dodano sortowanie wariantów podczas tworzenia vouchera.

## v4.0.8

#### 08.05.2023

1. Odświeżono przyciski przechodzenia do kategorii, produktów i wariantów.
2. Dodano masowe włączanie i wyłączanie promocji dla serwera.
3. Przywrócono weryfikację dwuetapową.

## v4.0.7

#### 01.05.2023

1. Dodano obsługę nowych identyfikatorów usług SimPay.
2. Dodano możliwość zmiany planu licencji.
3. Poprawiono obsługę wariantu o wartości 0 zł po zastosowaniu kodu rabatowego w API v4. Taki zakup jest oznaczany jako opłacony.
4. Usprawniono obsługę powiadomień operatorów płatności w API v4.
5. Oznaczono API v3 jako wersję bez dalszego rozwoju i wskazano API v4 jako wersję do nowych integracji.

## v4.0.6

#### 11.04.2023

1. Dodano do szczegółowych statystyk zarobek z poprzedniego miesiąca i zarobek ogólny.
2. Dodano informacje od HotPay do dokumentacji płatności.

## v4.0.5

#### 31.03.2023

1. Uzupełniono angielskie tłumaczenie panelu.

## v4.0.4

#### 11.02.2023

1. Dodano klonowanie serwera wraz z kategoriami, produktami i wariantami.

## v4.0.3

#### 09.02.2023

1. Dodano przycisk „Powrót” na listach produktów, kategorii i wariantów.
2. Dodano dodatkowe pole serwera dostępne w panelu i API, przeznaczone do własnych integracji.
3. Usunięto lvlup.pro z listy bram płatności.

## v4.0.2

#### 08.02.2023

1. Dodano endpoint API do zatwierdzania płatności i wykonywania komend powiązanych z zamówieniem.

## v4.0.1

#### 17.01.2023

1. Poprawiono rozróżnienie kolorów metod płatności na wykresach statystyk.
2. Poprawiono komunikaty porównujące wyniki sprzedaży w kokpicie, aby uwzględniały zarówno wzrost, jak i spadek.

## v4.0.0

#### 17.01.2023

Dodano następujące integracje płatności:

| Metoda | Dodane integracje |
| --- | --- |
| Przelewy | DPay, PayU, Przelewy24, PayNow. |
| paysafecard | DPay. |
| PayPal | CashBill, DPay. |
| BLIK Level 0 | CashBill, Paybylink. |
| SMS Premium | GetPay, CashBill, Paybylink, HotPay, MicroSMS, SimPay, DPay. |
| Direct Carrier Billing | Paybylink, HotPay, DPay. |
| PremiumRate | HotPay. |
| Pozostałe płatności online | Stripe. |
| Hosting | IceHost. |

Pozostałe zmiany:

1. Dodano wybór strony statusu płatności obsługiwanej przez SpaceIs lub szablon sklepu.
2. Dodano możliwość tymczasowego wyłączenia sprzedaży w sklepie.
3. Dodano powiadomienia e-mail dla kupującego i właściciela sklepu oraz webhooki Discord po zakupie.
4. Dodano miesięczny limit zarobku sklepu.
5. Dodano możliwość zakupu kilku licencji na jednym koncie oraz udostępniania licencji innym użytkownikom.
6. Dodano zgłoszenia pomocy technicznej w panelu i możliwość zmiany języka.
7. Rozszerzono raporty PDF o dodatkowe dane.
8. Dodano ustawianie prowizji dla bram oraz prezentację kwot po prowizji w transakcjach i statystykach.
9. Dodano vouchery z limitem użyć, terminem ważności oraz losowaniem wariantu.
10. Zaktualizowano [plugin SpaceIs](/plugin) i udostępniono jego kod źródłowy. Usprawniono sprawdzanie obecności gracza.
11. Dodano widgety OBS, czarną listę nicków i adresów e-mail, dzienne nagrody oraz cele serwerów.
12. Przeniesiono konta z v3 wraz z serwerami, kategoriami, produktami i wariantami. Zachowano obsługę API v3 bez nowych metod SMS Premium i BLIK Level 0.
