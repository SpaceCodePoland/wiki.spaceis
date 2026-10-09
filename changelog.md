# Changelog

Historia funkcji i poprawek SpaceIs. Wpisy historyczne opisują stan z chwili danego wydania. Aktualną dostępność integracji sprawdzisz na stronie [operatorów płatności](/payments/providers).

## v4.0.23

#### 09.10.2026

1. Dodano [koszyk](/payments/cart) pozwalający opłacić kilka produktów i sztuk jednym zamówieniem.
2. Dodano możliwość łączenia produktów z różnych serwerów tej samej licencji, jeśli właściciel włączy tę opcję.
3. Rozszerzono podsumowanie zamówienia o pozycje, warianty, ilości i wartości produktów. Dostępne metody płatności uwzględniają wszystkie pozycje koszyka.
4. Dodano dziewięć skórek strony płatności: Luna, Nova, Orbit, Aurora, Forma, Atelier, Signal, Slate i Noir.
5. Dodano [ustawienia wyglądu](/payments/checkout): palety kolorów, logo, teksty i widoczność elementów oraz podgląd roboczy przed zapisaniem zmian.
6. Dodano wybór między kafelkami a suwakiem dla zwykłych wariantów. Ustawienie można zmienić osobno dla produktu.
7. Odświeżono strony statusu płatności oraz podsumowanie zamówienia. Zachowano możliwość powrotu do strony statusu obsługiwanej przez szablon sklepu.
8. Dotychczasowe linki do pojedynczych produktów otwierają stronę płatności z jedną pozycją. Dodanie koszyka do własnego szablonu wymaga jego osobnej integracji.
9. Usunięto zapamiętywanie nicku i adresu e-mail kupującego na stronie płatności.
10. Dodano [własne domeny płatności](/payments/domain), instrukcję ich podłączenia oraz podgląd gotowości domeny i bezpiecznego połączenia.
11. Dodano opcję automatycznego podłączenia domeny obsługiwanej przez Cloudflare.
12. Dodano osobne pola na linki do regulaminu i polityki prywatności sklepu.
13. Dodano możliwość obsługi koszyka w sklepach korzystających z własnej integracji.
14. Rozszerzono informacje o transakcji o produkty, warianty, ilości i wartości pozycji koszyka.
15. Uwzględniono koszyki w [statystykach, zestawieniu transakcji i eksporcie CSV](/panel/statistics), a także w rankingach produktów i kupujących.
16. Dostosowano powiadomienia e-mail i Discord oraz widgety OBS do zakupów koszykowych.
17. Dodano realizację pozycji koszyka na właściwych serwerach. Problem z jednym serwerem nie zatrzymuje realizacji pozostałych pozycji.
18. Poprawiono obsługę rabatów procentowych z częścią dziesiętną oraz zakupów o wartości 0 zł po zastosowaniu kodu rabatowego.
19. Usprawniono odświeżanie statusu transakcji po zmianie jej stanu.
20. Linki do płatności otwierają zakup pod aktywną własną domeną sklepu.
21. Oznaczono nowe opcje strony płatności znacznikiem **BETA** i uzupełniono ich tłumaczenia.
22. Usunięto stary panel. Zarządzanie sklepem odbywa się w nowym [panelu SpaceIs](/panel).
23. Usunięto dawną usługę hostowania sklepów w SpaceIs. Szablony instalowane na własnym hostingu nadal działają.
24. Uzupełniono Wiki o instrukcje panelu, koszyka, domen i wariantów oraz zaktualizowano listę operatorów płatności.
25. Odświeżono kokpit i wszystkie widoki statystyk, poprawiając wygląd kart, wykresów, rankingów i filtrów w obu motywach oraz na telefonach.

## v4.0.22

Nowy panel oraz rozbudowane zarządzanie sklepem i płatnościami.

1. Wprowadzono nowy [panel zarządzania](/panel) z jasnym i ciemnym motywem oraz układem dostosowanym do telefonów.
2. Odświeżono karty licencji, serwerów, kategorii, produktów i wariantów, a także portfel, szablony i zgłoszenia pomocy.
3. Ujednolicono formularze, komunikaty walidacji, przyciski i widoki bez danych. Poprawiono czytelność tabel na mniejszych ekranach.
4. Dodano wybór bieżącej licencji, rozbudowano wyszukiwanie i uporządkowano menu.
5. Rozbudowano kokpit o podsumowania sprzedaży, ostatnie zakupy, najlepsze produkty i metody płatności.
6. Dodano centrum powiadomień o sprzedaży, błędach płatności i zbliżającym się końcu licencji.
7. Uzupełniono polskie i angielskie tłumaczenia oraz poprawiono wyświetlanie dat, kwot i liczb.
8. Poprawiono zmianę kolejności elementów katalogu oraz wygląd stron błędów i przerwy technicznej.
9. Dodano [logowanie i łączenie kont z Google oraz Discordem](/panel/account).
10. Połączenie z istniejącym kontem wymaga zalogowania do SpaceIs i potwierdzenia w ustawieniach. Zgodny adres e-mail nie łączy kont automatycznie.
11. Dodano kody e-mail, klucze sprzętowe i klucze dostępu do weryfikacji dwuetapowej. Działa ona także przy logowaniu przez Google i Discord.
12. Uproszczono rejestrację, odświeżono logowanie i odzyskiwanie hasła oraz poprawiono konfigurację weryfikacji dwuetapowej.
13. Uporządkowano uprawnienia subkont oraz dostęp do danych wybranej licencji.
14. Dodano dziennik zmian licencji, pozwalający właścicielowi przeglądać działania wykonane w sklepie.
15. Poprawiono obsługę anulowanego lub wygasłego logowania przez Google i Discord.
16. Dodano [przedziały wariantów](/panel/variants) z początkiem, końcem, krokiem, ceną jednostkową oraz szablonami nazwy i komend.
17. Dodano zniżkę podstawową, progi promocyjne i podgląd cen dla przedziałów. Kupujący widzi poszczególne wartości jako osobne warianty.
18. Dodano masową zmianę cen wariantów produktu oraz kopiowanie cen z istniejącej bramy przy dodawaniu nowej.
19. Dodano promocje z datą rozpoczęcia i zakończenia.
20. Dodano limity użyć i termin ważności kodów rabatowych.
21. Dodano dzienne limity zakupów produktu dla gracza oraz podgląd sklepu z panelu.
22. Dodano możliwość czasowego blokowania nicków i adresów e-mail na czarnej liście.
23. Rozbudowano statystyki o przegląd sprzedaży, zestawienia produktów, metod płatności i klientów oraz filtrowanie według serwera i okresu.
24. Odświeżono wykresy, legendy i podpowiedzi z wartościami w jasnym i ciemnym motywie.
25. Dodano mapę aktywności zakupów według dnia tygodnia i godziny oraz lejek pokazujący wejścia na stronę płatności, rozpoczęte płatności i opłacone transakcje.
26. Rozbudowano podgląd transakcji i eksport CSV. Poprawiono wcześniejsze eksporty transakcji do arkusza.
27. Dodano opcjonalny codzienny raport sprzedaży wysyłany e-mailem.
28. Dodano osobną sekcję [powiadomień Discord](/panel/webhooks) dla całej licencji, serwera, produktu lub wariantu, z własną treścią, tytułem i kolorem wiadomości.
29. Dodano możliwość włączania i wyłączania powiadomień Discord z listy oraz wyboru, których zakupów dotyczą.
30. Ujednolicono wygląd wiadomości systemowych i dodano e-mailowe potwierdzenia zakupu licencji oraz szablonów.
31. Dodano płatności Paymentic: online, paysafecard oraz doliczane do rachunku telefonu.
32. Dodano tryb testowy Paymentic oraz opcję ukrycia paysafecard na jego stronie płatności online.
33. Dodano integrację płatności ChunkServe.pl.
34. Dodano [operatora niestandardowego](/payments/custom-operator). Dostępne są wyłącznie integracje i domeny zatwierdzone przez SpaceIs.
35. Zaktualizowano listę [dostępnych operatorów płatności](/payments/providers) i obsługiwanych metod.
36. Doładowania portfela SpaceIs oparto wyłącznie na Paymentic. Dotyczy to portfela właściciela konta, a nie listy metod płatności w jego sklepie.
37. Poprawiono obsługę potwierdzeń płatności, kwot i komunikatów błędów w integracjach operatorów, w tym Paymentic, CashBill BLIK, SkillHost, HotPay i DPay.
38. Poprawiono obsługę płatności, które mogły powodować podwójne naliczenie zakupu lub doładowania portfela.
39. Poprawiono obsługę płatności o wartości 0 zł po rabacie oraz sytuacji, gdy na stronie płatności nie ma dostępnych metod.
40. Zakończono obsługę starego pluginu. Do połączenia serwera gry należy używać aktualnego [pluginu SpaceIs](/plugin).
41. Poprawiono uwzględnianie promocji, kodów rabatowych i limitów podczas zakupów.
42. Usprawniono obsługę błędów dostarczania zakupów na serwer gry.

## v4.0.21

#### 22.12.2023

1. Dodano płatności paysafecard i PayPal przez SimPay.pl.
2. Uproszczono konfigurację operatora SimPay.

## v4.0.20

#### 15.12.2023

1. Dodano nowy styl strony płatności pay.spaceis.pl.
2. Ujednolicono opisy zakupów widoczne podczas płatności.

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

1. Dodano generowanie voucherów ważnych przez wybraną liczbę miesięcy.

## v4.0.13

#### 25.07.2023

1. Dodano możliwość ręcznego połączenia aplikacji uwierzytelniającej z kontem.
2. Po zmianie hasła pozostałe zalogowane sesje są automatycznie wylogowywane.
3. Dodano możliwość wykorzystania kodu rabatowego i wysokości zniżki w komendach realizujących zakup.

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

1. Zaktualizowano konfigurację płatności SimPay.
2. Dodano możliwość zmiany planu licencji.
3. Poprawiono realizację zakupów, których wartość po użyciu kodu rabatowego wynosi 0 zł.
4. Usprawniono potwierdzanie płatności przez operatorów.

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
2. Dodano dodatkowe pole w ustawieniach serwera do wykorzystania we własnym sklepie.
3. Usunięto lvlup.pro z listy bram płatności.

## v4.0.2

#### 08.02.2023

1. Dodano możliwość zatwierdzania płatności we własnych integracjach sklepu.

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
10. Zaktualizowano [plugin SpaceIs](/plugin) i poprawiono sprawdzanie obecności gracza na serwerze.
11. Dodano widgety OBS, czarną listę nicków i adresów e-mail, dzienne nagrody oraz cele serwerów.
12. Przeniesiono konta z poprzedniej wersji SpaceIs wraz z serwerami, kategoriami, produktami i wariantami.
