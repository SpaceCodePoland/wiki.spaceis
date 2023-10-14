---
icon: clock
---

# Changelog

## v4.0.15

#### 14.10.2023
1. Dodaliśmy obsługę przelewów SimPay.pl 

## v4.0.14

#### 31.08.2023
1. Dodaliśmy obsługę generowania kodów vouchera przez API (https://api.spaceis.pl/#/Vouchery/generowanieKodwVoucheraokresWanociMiesic)

## v4.0.13

#### 25.07.2023
1. Kody weryfikacji dwuetapowej pokazują również token/sekret.
2. Po zmianie hasła w panelu następuje automatyczne wylogowanie innych zalogowanych sesji.
3. Dodano do komend 2 nowe prefiksy: {DISCOUNT_CODE} - użyty kod rabatowy (jeśli nie użyto żadnego, to będzie mieć wartość NONE) i {DISCOUNT_CODE_PERCENTAGE} - % użytego kodu rabatowego.


## v4.0.12

#### 23.07.2023
1. Dodanie bezpośredniego PaySafeCarda do operatorów płatności jako pierwszy ItemShop w Polsce


## v4.0.11

#### 16.07.2023
1. Dodano operatora płatności SkillHost.pl


## v4.0.10

#### 10.07.2023
1. Dodano opcję wykonania ponownie komend (transakcja musi być opłacona).


## v4.0.9

#### 27.06.2023
1. Dodano sortowanie wariantów podczas dodawania vouchera.

## v4.0.8

#### 08.05.2023
1. Zmieniono przyciski do przechodzenia do kategorii, produktów i wariantów,
2. Masowe włączanie/wyłączanie promocji na serwer,
3. Dodano z powrotem weryfikację dwuetapową.


## v4.0.7 

#### 01.05.2023

1. Dodano obsługę nowych ID usług w bramach SimPay,
2. Dodano opcję zmiany planu licencji,
3. Naprawiono problem, kiedy kod rabatowy sprawiał, że wariant kosztował 0 zł (od teraz płatność zostanie oznaczona jako opłacona) – Dotyczy tylko API v4
4. Obsługa notyfikacji płatności powinna działać szybciej (dotyczy tylko API v4), 
5. API v3 zostaje oznaczone jako deprecated. Nie będzie otrzymywać żadnych nowych aktualizacji (w tym nowych operatorów płatności). Zachęcamy przejście na API v4 (https://api.spaceis.pl/).


## v4.0.6

#### 11.04.2023

1. Dodaliśmy do szczegółowych statystyk zarobek w zeszłym miesiącu oraz zarobek ogólny
2. Dodaliśmy informację od HotPaya do https://wiki.spaceis.pl/payments/choose/

## v4.0.5 

#### 31.03.2023

1. Skończyliśmy tłumaczenie angielskiego. Od teraz możesz posługiwać się po panelu po angielsku

## v4.0.4

#### 11.02.2023

1. Dodano opcję klonowania serwera (wraz z kategoriami, produktami i wariantami).

## v4.0.3

#### 09.02.2023

1. W liście produktów, kategorii i wariantów dodano przycisk "Powrót".
2. Dodano w API oraz w panelu dodatkowe pole w serwerach, do wykorzystania w swoich integracjach.
3. Usunęliśmy lvlup.pro z listy bram płatności.

## v4.0.2

#### 08.02.2023

1. Dodano nowy endpoint w API do "opłacania" zamówień, ustawia transakcję jako opłaconą i wykonuje komendy na serwerze. Link do spec. API: https://api.spaceis.pl/#/Transakcje/zatwierdzaPatnoOrazWykonujeKomendNaSerwerzeUytekNaWasnOdpowiedzialno

## v4.0.1

#### 17.01.2023

1. Zmieniono kolor charta w statystykach z wykorzystanych metod płatności. Kolory są losowane automatycznie, dzięki czemu widać co jest jaką metodą bez tego samego koloru
2. Zmieniono w kokpicie napis "jest to o x% więcej", który czasem był ujemny na "jest to o x% więcej/mniej"

## v4.0.0

#### 17.01.2023

1. Nowe bramki płatności:
- GetPay (SMS Premium)
- CashBill (SMS Premium)
- CashBill (BLIK Level 0)
- CashBill (PayPal)
- Paybylink (SMS Premium)
- Paybylink (Direct Carrier Billing)
- Paybylink (BLIK Level 0)
- HotPay (SMS Premium)
- HotPay (Direct Carrier Billing)
- HotPay (PremiumRate)
- MicroSMS (SMS Premium)
- SimPay (SMS Premium)
- Dpay (Przelewy)
- Dpay (PaySafeCard)
- Dpay (SMS Premium)
- Dpay (PayPal)
- Dpay (Direct Carrier Billing)
- Stripe
- PayU (Przelewy)
- Przelewy24 (przelewy)
- PayNow (Przelewy)
- IceHost (Hosting)

2. Możliwość ustawienia statusu strony (po stronie API lub szablonu).
3. Możliwość tymczasowego wyłączenia sklepu.
4. Możliwość mailingu do klienta oraz administratora po każdej dokonanej transakcji.
5. Możliwość Discord webhooków po każdej dokonanej transakcji.
6. Możliwość ustawienia maksymalnej kwoty zarobku w miesiącu (głównie przydatne dla osób z działalnością nierejestrowaną).
7. Możliwość kupna dodatkowych licencji po jednego konta.
8. Możliwość udostępnienia swojej licencji innym użytkownikom SpaceIs.
9. Możliwość robienia zgłoszeń poprzez panel.
10. Możliwość zmiany języka.
11. Możliwość generowania raportów PDF z większą ilością danych.
12. Możliwość dodania prowizji do każdej bramki płatności (statystyki + transakcje pokazują zarobek po odjęciu tej prowizji).
13. Możliwość tworzenia voucherów z limitem użyć, czasowym oraz możliwość losowania wariantu dla vouchera.
14. Poprawienie pluginu spaceis, ma on również otwarty kod źródłowy (https://github.com/SpaceCodePoland/spaceis-plugin). Nie wymaga on teraz połączenia z bazą danych (w przypadku sprawdzenia gracza online).
15. Możliwość dodania widgetów do OBS - idealne dla streamerów.
16. System czarnej listy (możesz zablokować dany nick lub adres e-mail przed płatnościami w Twoim sklepie).
17. System dziennych nagród.
18. System celów serwera.

API v3 będzie wciąż obsługiwane, jednak nie będą z nim działać SMSy premium oraz BLIK Level 0. Wszelakie konta z v3 zostały automatycznie zmigrowane (wraz z wszystkimi serwerami, kategoriami, produktami, wariantami etc.)
