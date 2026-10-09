---
label: Dostępni operatorzy płatności
order: 1
---

# Dostępni operatorzy płatności

Poniżej znajdziesz integracje dostępne przy dodawaniu nowej bramy w SpaceIs. Wybierz licencję i przejdź do **Płatności > Bramy płatności > Nowa brama**. Ten sam operator może mieć osobne bramy dla różnych metod.

## Metody płatności

==- Przelewy online
Paymentic, CashBill.pl, Paybylink.pl, HotPay.pl, DPay.pl, PayU.pl, Przelewy24.pl, PayNow.pl.
==- paysafecard
Paymentic, myPaySafeCard (bezpośrednia integracja), CashBill.pl, Paybylink.pl, HotPay.pl, DPay.pl.
==- PayPal
PayPal Company, PayPal private/donations, CashBill.pl, DPay.pl. Przy bezpośredniej integracji PayPal wybierz bramę odpowiadającą rodzajowi konta i zapoznaj się z informacjami w jej konfiguracji.
==- BLIK Level 0
CashBill.pl, Paybylink.pl. Kupujący wpisuje kod BLIK bezpośrednio w formularzu płatności.
==- SMS Premium
CashBill.pl, Paybylink.pl, HotPay.pl, DPay.pl, MicroSMS.pl, GetPay.pl.
==- Direct Carrier Billing i PremiumRate
Paymentic (Direct Carrier Billing) oraz HotPay.pl PremiumRate.
==- Pozostałe płatności online
Stripe, ZEN. Metody dostępne na stronie operatora zależą od konfiguracji jego konta i usługi.
==- Hostingi
IceHost.pl, SkillHost.pl, TostHost.pl, ChunkServe.pl.
===

!!!
Lista opisuje integracje SpaceIs. Dostępność konkretnej usługi, warunki jej aktywacji i rozliczeń ustalasz z operatorem. Brama dodana już do licencji nie pojawia się ponownie na liście nowych bram.
!!!

## Operator niestandardowy

Brama [Operator niestandardowy](/payments/custom-operator) pozwala połączyć sklep z zewnętrznym serwisem zatwierdzonym przez SpaceIs, np. hostingiem obsługującym płatność z portfela. Adres płatności i sekret integracji otrzymasz od tego serwisu.

Aktualną listę zatwierdzonych operatorów i ich domen znajdziesz w konfiguracji bramy. Opcja dodania tej bramy jest dostępna, gdy SpaceIs udostępnia co najmniej jednego zatwierdzonego operatora.

## Dostępność metody w sklepie

Po dodaniu bramy uzupełnij dane otrzymane od operatora i wykonaj instrukcje pokazane w jej konfiguracji, w tym ustawienia powiadomień o płatnościach, jeśli są wymagane.

Dla zwykłych wariantów ustaw ceny ręcznie lub skopiuj je z istniejącej bramy przy tworzeniu nowej. [Przedziały wariantów](/panel/variants) obejmują bramy inne niż SMS automatycznie. W [koszyku](/payments/cart) wybrana metoda musi być dostępna dla wszystkich pozycji; API koszyka nie obsługuje SMS.

Jeżeli metoda nie jest wyświetlana, sprawdź konfigurację bramy, ceny i komunikaty w **Błędy płatności**.
