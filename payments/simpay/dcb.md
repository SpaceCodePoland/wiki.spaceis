---
label: Konfiguracja płatności SimPay Direct Carrier Billing
authors:
  - name: Patryk Vizauer
    email: patryk@spacecode.pl
---

[!button target="blank" text="Link do rejestracji w systemie SimPay"](https://panel.simpay.pl/auth/register)

Krok 1. W panelu SimPay przejdź do Direct Billing > Usługi. Wybierz usługę, którą chcesz dodać do SpaceIsa. Wybierz i
naciśnij przycisk "Szczegóły".

![Lista usług DirectBilling w SimPay](/static/payments/simpay1.png)

Krok 2. Wprowadź ID usługi oraz klucz do sygnatury do panelu SpaceIs. Ustaw adres URL IPN na ten, który masz podany w
panelu SpaceIs.

![Usługa DirectBilling w SimPay](/static/payments/simpay2.png)

![Konfiguracja w SpaceIs](/static/payments/simpay3.png)

Krok 3. Przejdź do zakładki Konto Klienta > API. Naciśnij przycisk "Utwórz nowy dostęp".

![Lista kluczy API w SimPay](/static/payments/simpay4new.png)

Następnie uzupełnij nazwę Twojego klucza. Zalecamy włączyć tylko uprawnienie "directbilling.transactions.create", oraz
opcjonalnie wybrać interesującą Cię usługę.

![Ustawienie uprawnień klucza API w SimPay](/static/payments/simpay4new2.png)

Po naciśnięciu przycisku "Utwórz dostęp", skopiuj Klucz oraz Hasło do pól: Klucz API, oraz Hasło API w SpaceIs.

![Klucze w SimPay](/static/payments/simpay4new3.png)
![Konfiguracja w SpaceIs](/static/payments/simpay5.png)

Gotowe. Płatności Direct Billing SimPay są gotowe do działania.