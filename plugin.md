---
icon: key-asterisk
---
# Konfiguracja pluginu

## Informacje ogólne

Pobieramy plugin [z tej strony](https://github.com/SpaceCodePoland/spaceis-plugin/releases) i wgrywamy go na serwer. Po wgraniu należy **zrestartować** serwer.

## Konfiguracja

Po zrestartowaniu serwera należy otworzyć plik `config.yml` znajdujący się w folderze `plugins/SpaceIsPlugin`.

Uzupełniamy 3 zmienne, pozostałe 2 można zmienić, ale mogą pozostać domyślne:

| Pole      | Opis                                                                                                                                               |
|-----------|----------------------------------------------------------------------------------------------------------------------------------------------------|
| serverKey | Klucz serwera dostępny w panelu SpaceIs.pl > Moja licencja > Serwery > Edycja poszczególnego serwera                                               |
| serverId  | ID serwera dostępny w panelu SpaceIs.pl > Moja licencja > Serwery > Edycja poszczególnego serwera                                                  |
| apiKey    | Klucz API z panelu SpaceIs.pl > Zarządzanie licencją                                                                                               |
| apiUri    | Link do API, służy tylko do dedykowanych instancji SpaceIsa, bądź indywidualnych zamówień. Zostaw domyślny                                         |
| debug     | Opcja logowania wszelkich akcji, w konsoli zostaną pokazane wrażliwe informacje (klucz API, klucz serwera) oraz adresy, z którymi łączy się plugin |


Po skonfigurowaniu pluginu należy zrestartować serwer. W przypadku zmiany już działającego configu można wywołać komendę ```/spaceis reload``` (wymagana permisja `spaceis.reload`).

