---
label: Konfiguracja płatności CashBill Przelewy/PaySafeCard
authors:
- name: Patryk Vizauer
  email: patryk@spacecode.pl
---

[!button target="blank" text="Link do rejestracji w systemie CashBill"](https://panel.cashbill.pl/ref/spaceis.pl)

Krok 1. Z panelu CashBill wybieramy interesujący nas punkt płatności (Płatności > Lista). Wybieramy za pomocą zębatki
podkreślonej niebieskim kolorem na poniższym zdjęciu.

![Lista CashBill](/static/payments/cashbill1.png)

Krok 2. Z panelu CashBill wpisujemy Identyfikator Punktu Płatności oraz Klucz Punktu Płatności. Należy ustawić **rodzaj
interfejsu komunikacji** na Web Service, oraz ustawić **adres serwerowego potwierdzenia transakcji** na ten, który jest
podany w SpaceIs. Każdy użytkownik i każda brama ma swój własny, indywidualny adres. Prosimy skopiować go z panelu.
W panelu SpaceIs wpisujemy dodatkowo nazwę odbiorcy (podkreślona na niebiesko) - może to być nazwa
firmy, imię nazwisko sprzedającego. Kolorem zielonym, podkreślony jest tryb testowy (jeśli jest aktywny, możemy testować
integrację płatności bez konieczności wydawania pieniędzy. Aby móc przyjmować pieniądze, należy ustawić na Nieaktywny).

![Konfiguracja CashBill](/static/payments/cashbill2.png)

![Konfiguracja SpaceIs](/static/payments/cashbill2.webp)

Gotowe! Płatności zostały prawidłowo zintegrowane. Zalecamy włączenie trybu testowego i przetestowanie, czy płatność zostaje realizowana pomyślnie.