---
icon: file-directory-open-fill
---
# Instalacja szablonów

# Instalacja szablonu SpaceIs

Szablony wymagają instalacji:

- PHP 8.1
- nginx/apache2 z obsługą mod_rewrite oraz htaccess

Szablon zainstalujesz na:

- dowolnym hostingu WWW, który wspiera PHP 8.1 (np. SeoHost.pl, MyDevil.net),
- serwerze VPS,
- serwerze dedykowanym.

!!!danger Titanaxe
Szablony `NIE` będą działać na hostingu WWW TitanAxe. Jest to spowodowane brakiem reakcji supportu jak i samym złym systemie hostingu WWW.
!!!

!!! Kody promocyjne
SeoHost.pl - kod rabatowy `spaceis` 30% taniej przy pierwszym roku.

MyDevil.net - kod rabatowy `spaceis` 20% taniej.
!!!

W przypadku korzystania z nginx należy go odpowiednio skonfigurować:

```nginx
server {
    listen 80;
    listen [::]:80;
    server_name mojadomena.pl;
    root /sciezka/do/sklepu;
 
    add_header X-Frame-Options "SAMEORIGIN";
    add_header X-Content-Type-Options "nosniff";
 
    index index.php;
 
    charset utf-8;
 
    location / {
        try_files $uri $uri/ /index.php?$query_string;
    }
 
    location = /favicon.ico { access_log off; log_not_found off; }
    location = /robots.txt  { access_log off; log_not_found off; }
 
    error_page 404 /index.php;
 
    location ~ \.php$ {
        fastcgi_pass unix:/var/run/php/php8.1-fpm.sock;
        fastcgi_param SCRIPT_FILENAME $realpath_root$fastcgi_script_name;
        include fastcgi_params;
    }
 
    location ~ /\.(?!well-known).* {
        deny all;
    }
}
```

W przypadku instalacji szablonu na VPS/maszynie dedykowanej należy przydzielić permisje:
```
chown -R www-data:www-data *
```

## Konfiguracja sklepu

Plik konfiguracyjny sklepu znajduje się w `app/config.php`. Tam znajdują się elementy konfiguracyjne odpowiednio wytłumaczone.

## Instalacja szablonu na SeoHost.pl/jakimkolwiek hostingu opartym na Direct Admin

<iframe width="560" height="315" src="https://www.youtube.com/embed/Da5_3ot0yNM?si=xziSFQ5BJMRuhbgh" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen></iframe>