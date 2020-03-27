---
title: Обнављање Let's encrypt SSL сертификата
category: Интернет
order: 1
---

Ово је процедура за обнављање SSL сертификата који се користи за Nextcloud сервер.

Неопходно је да се промене no-ip.org DNS записи и подеси прослеђивање порта.

1. Подесити DNS записе као на слици:

![Подешавање DNS записа](../../images/no-ip.png)

1. Подесити прослеђивање порта као на слици:

![Подешавање прослеђивања порта](../../images/router.png)

1. Извршити команду на Nextcloud серверу:

~~~bash

root@nextcloud:/usr/local/etc/apache24/Includes # certbot-2.7 renew
Saving debug log to /var/log/letsencrypt/letsencrypt.log

- - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - -
Processing /usr/local/etc/letsencrypt/renewal/ncld.ddns.net.conf
- - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - -
Cert is due for renewal, auto-renewing...
Plugins selected: Authenticator webroot, Installer None
Renewing an existing certificate
Performing the following challenges:
http-01 challenge for ncld.ddns.net
Using the webroot path /usr/local/www/nextcloud for all unmatched domains.
Waiting for verification...
Cleaning up challenges

- - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - -
new certificate deployed without reload, fullchain is
/usr/local/etc/letsencrypt/live/ncld.ddns.net/fullchain.pem
- - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - -

- - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - -

Congratulations, all renewals succeeded. The following certs have been renewed:
  /usr/local/etc/letsencrypt/live/ncld.ddns.net/fullchain.pem (success)
- - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - -
root@nextcloud:/usr/local/etc/apache24/Includes #
~~~

1. Вратити све на стара подешавања

> Непоходно је да се поново покрене веб сервер како би учитао нови сертификат
