---
title: "Черновик учебника"
---


## Настройка среды программирование

### Выбор операционной системы и средств разработки

#### Какие ОС подходят для разработки?

#### От чего зависит выбор рабочей ОС?

#### Чем коварен перенос программы в другую ОС?

### Установка необходимых программ

#### Что нужно для написания программ?

#### Как установить интерпретатор Python?

#### Каким текстовым редактором пользоваться?

#### Зачем нужна интегрированная среда разработки?

#### Как пользоваться менеджером пакетов?

### Работа с виртуальными окружениями

#### Зачем нужны локальные окружения?

#### Как создать виртуальное окружение в Python?

#### Как работать с виртуальным окружением в Python?

### Типичная структура программного проекта

#### Зачем следовать типичной структуре?

#### Что такое метаинформация?

#### Что такое зависимости проекта?

#### Что такое зависимости разработки?


## Безопасность сетевых приложений


### Как криптография помогает обеспечивать безопасность?

{% capture notice-2 %}
Выводы:
1. При работе сетевых приложений остро встают вопросы обеспечения безопасности.
2. Конфиденциальность - это когда вы уверены, что ваши данные не прочитает кто угодно.
3. Целостность - это когда вы уверены, что сообщение по сети дошло в неизменном виде.
4. Аутентификация - это когда вы уверены, что собеседник именно тот, за кого себя выдает.
5. Криптография занимается разработкой алгоритмов - криптографических примитивов.
6. Также существуют криптографические протоколы - правила применения примитивов.
{% endcapture %}
<div class="notice--info">{{ notice-2 | markdownify }}</div>

### Каковы основные правила криптографии?

{% capture notice-2 %}
Выводы:
1. Криптографические протоколы и алгоритмы должны быть открыты.
2. Абсолютной защиты не существует. Криптоанализ носит вероятностный характер.
3. Криптография - не решение всех проблем. Есть, например, социальная инженерия.
4. Криптографические алгоритмы бесполезны, если применяются неправильно.
5. Не стоит изобретать велосипед. Рекомендуется использовать готовые реализации.
6. Не стоит использовать один ключ для шифрования всего.
7. Шифр считается небезопасным, если можно получить хоть какую-то информацию.
{% endcapture %}
<div class="notice--info">{{ notice-2 | markdownify }}</div>

### Что такое симметричное шифрование?

{% capture notice-2 %}
Выводы:
1. Шифрование нужно для сокрытия данных.
2. Симметричный шифр состоит из двух алгоритмов - шифрования и дешифрования.
3. Симметричные шифры используют один ключ для шифрования и для дешифровки.
4. Симметричные шифры более простые и быстрые.
5. Эффективность симметричных шифров экспоненциально растет от длины ключа.
6. Рекомендуемый стандартный шифр на сегодня - AES  с ключом 256 бит.
7. Шифр AES реализован аппаратно в процессорах AMD и Intel.
8. Для работы симметричных шифров нужно, чтобы обе стороны знали общий ключ.
{% endcapture %}
<div class="notice--info">{{ notice-2 | markdownify }}</div>

### Что такое асимметричное шифрование?

{% capture notice-2 %}
Выводы:
1. В асимметричном шифровании один ключ используется для шифрования, другой для расшифровки.
2. В состав асимметричного шифра входит алгоритм генерации ключей.
3. Ключи всегда существуют в паре - открытый и закрытый.
4. Открытый ключ можно публиковать и отправлять всем, закрытый - держать в строгой тайне.
5. Если закрытый ключ скомпрометирован - надо сгенерировать новую пару.
6. Обычно сообщение шифруют открытым ключом Боба, то есть получателя..
7. Такое сообщение сможет расшифровать только Боб своим закрытым ключом.
8. Распространенный алгоритмы асимметричного шифрования - RSA.
{% endcapture %}
<div class="notice--info">{{ notice-2 | markdownify }}</div>

### Как асимметричное шифрование обеспечивает аутентификацию?

{% capture notice-2 %}
Выводы:
1. Можно иметь две пары ключей - ключи отправителя и ключи получателя.
2. Алиса шифрует сообщение своим закрытым ключом и открытым ключом Боба.
3. Боб расшифровывает сообщение своим закрытым и открытым ключом Алисы.
4. Секретность обеспечивается тем, что закрытый ключ Боба не знает никто кроме него.
5. При этом Боб уверен, что сообщение отправила Алиса, ведь никто не знает ее закрытого ключа.
6. Такая система хорошо работает только между доверенными сторонами.
7. С ростом числа участников количество пар ключей растет в квадратичной зависимости.
8. Для аутентификации можно сообщить другой стороне свой открытый ключ.
{% endcapture %}
<div class="notice--info">{{ notice-2 | markdownify }}</div>

### Что такое электронный сертификат?

{% capture notice-2 %}
Выводы:
1. Открытый ключ не может подтвердить принадлежность другой стороны.
2. Мы можем быть уверены, что сообщение отправлено тем, кто знает закрытый ключ в пару к этому открытому, но кто это?
3. Для этого нужно, чтобы кто-то кому мы доверяем подтвердил, что данный открытый ключ принадлежит определенному лицу.
4. Центр сертификации заверяет открытые ключи и подтверждает личность их владельцев.
5. Для этого он добавляет к ключу служебную информацию, шифрует его своим ключом и получается цифровой сертификат.
6. Цифровой сертификат используется как усиленный открытый ключ.
7. Центрами сертификации выступают авторитетные организации в сфере ИБ.
8. Обычно получение сертификата - платная услуга, но можно получить бесплатный.
9. Существуют самоподписанные сертификаты - они хороши для тестирования и обучения.
{% endcapture %}
<div class="notice--info">{{ notice-2 | markdownify }}</div>

### Что такое хеш функция?

{% capture notice-2 %}
Выводы:
1. Хеш функция принимает строку любой длины и выдает результат фиксированной длины.
2. Результат называется хеш или дайджест.
3. При изменении сообщения даже немного дайджест изменяется полностью и непредсказуемо.
4. По дайджесту невозможно восстановить сообщение.
5. Хеши не используются для шифрования, это одностороннее преобразование.
6. Существует возможность коллизии, но ей можно пренебречь.
7. Хеши используются для защиты от случайных повреждений данных
8. Распространенные алгоритмы хеширования - MD5, SHA-1, SHA-256.
{% endcapture %}
<div class="notice--info">{{ notice-2 | markdownify }}</div>

### Что такое электронная подпись?

{% capture notice-2 %}
Выводы:
1. Хеши не гарантируют защиты от целенаправленного искажения данных.
2. Дайджест может быть дополнен цифровым сертификатом отправителя и зашифрован.
3. Это называется цифровая подпись.
4. Документ подписанный ЭЦП нельзя изменить - он перестанет соответствовать подписи.
5. Подпись подделать тоже нельзя - для этого надо знать закрытый ключ отправителя.
{% endcapture %}
<div class="notice--info">{{ notice-2 | markdownify }}</div>

### Что такое протокол рукопожатия?

{% capture notice-2 %}
Выводы:
1. Специальные алгоритмы могут обеспечить общий секрет при обмене данными по открытому каналу.
2. Такие алгоритмы основаны на односторонних функциях.
3. Самый распространенный алгоритм - протокол Диффи-Хеллмана.
4. Существуют более сложные модификации, например схема эль Гамаля.
5. Современные протоколы основаны на эллиптических кривых.
6. Протокол рукопожатия может дать возможность использовать симметричный шифр.
{% endcapture %}
<div class="notice--info">{{ notice-2 | markdownify }}</div>

### Как работает протокол TLS?

{% capture notice-2 %}
Выводы:
1. Протокол TLS или раньше SSL используется для обеспечения безопасности сетевых соединений.
2. Он может работать в паре с любым другим протоколом прикладного уровня.
3. При установке соединения стороны сначала обмениваются поддерживаемыми параметрами.
4. Затем они могут проверить сертификаты друг друга, если это необходимо и требуется.
5. Обмен сертификатами или просто открытыми ключами дает возможность шифровать трафик.
6. TLS в сочетании с HTTP называется HTTPS и очень широко используется.
7. В реальной жизни нет причин не использовать TLS.
{% endcapture %}
<div class="notice--info">{{ notice-2 | markdownify }}</div>


## Основы компьютерных сетей

### Основы сетевого взаимодействия

{% capture notice %}
Выводы:
1. Устройство, обеспечивающее компьютеру обмен данными по сети - сетевой адаптер
1. У каждого сетевого адаптера есть физический адрес - MAC.
1. Сетевые адаптеры могут быть проводные, беспроводные, виртуальные. Каждый конкретный адаптер поддерживает определенную архитектуру сети.
1. В компьютере может быть несколько сетевых адаптеров.
1. При подключении к сети адаптеру назначается сетевой адрес - IP, использующийся для сетевой маршрутизации.
1. Кроме адреса самого компьютера важными параметрами сетевого подключения являются маска сети, адрес шлюза, адрес DNS сервера.
1. Разные программы на одном хосте могут использовать разные сетевые порты для разграничения собственного сетевого трафика.
{% endcapture %}
<div class="notice--info">{{ notice | markdownify }}</div>

### Настройка сети в Linux

```bash
ifconfig
	enp0s3: flags=4163<UP,BROADCAST,RUNNING,MULTICAST>  mtu 1500
	        inet 10.4.23.11  netmask 255.255.255.0  broadcast 10.4.23.255
	        inet6 fe80::a00:27ff:fed7:e759  prefixlen 64  scopeid 0x20<link>
	        ether 08:00:27:d7:e7:59  txqueuelen 1000  (Ethernet)
	        RX packets 200633  bytes 247164183 (247.1 MB)
	        RX errors 0  dropped 4685  overruns 0  frame 0
	        TX packets 16379  bytes 1754936 (1.7 MB)
	        TX errors 0  dropped 0 overruns 0  carrier 0  collisions 0

	lo: flags=73<UP,LOOPBACK,RUNNING>  mtu 65536
	        inet 127.0.0.1  netmask 255.0.0.0
	        inet6 ::1  prefixlen 128  scopeid 0x10<host>
	        loop  txqueuelen 1000  (Local Loopback)
	        RX packets 2987  bytes 171636 (171.6 KB)
	        RX errors 0  dropped 0  overruns 0  frame 0
	        TX packets 2987  bytes 171636 (171.6 KB)
	        TX errors 0  dropped 0 overruns 0  carrier 0  collisions 0

```

```bash
ping 127.0.0.1
```

```bash
ping 127.0.0.1
ping 192.168.56.101
ping 192.168.56.1
ping 192.168.56.15
ping 8.8.8.8
ping ya.ru
```

```bash
nc localhost 22
	SSH-2.0-OpenSSH_8.2p1 Ubuntu-4ubuntu0.5
	hello
	Invalid SSH identification string.
	^C
```

```bash
nc -z -v localhost 1-100
```

```bash
nc -l 8080
```

```bash
arp -n 
	Address                  HWtype  HWaddress           Flags Mask            Iface
	10.4.23.31               ether   80:6d:97:08:2d:23   C                     enp0s3
	10.4.23.1                ether   b0:fa:eb:06:b1:cc   C                     enp0s3
```

```bash
sudo netstat -tlpn
	Active Internet connections (only servers)
	Proto Recv-Q Send-Q Local Address           Foreign Address         State       PID/Program name    
	tcp        0      0 127.0.0.53:53           0.0.0.0:*               LISTEN      42650/systemd-resol 
	tcp        0      0 0.0.0.0:22              0.0.0.0:*               LISTEN      630/sshd: /usr/sbin 
	tcp6       0      0 :::22 
```

```bash
sudo netstat -tpn
	Active Internet connections (w/o servers)
	Proto Recv-Q Send-Q Local Address           Foreign Address         State       PID/Program name    
	tcp        0      0 10.4.23.11:22           10.4.23.31:40926        ESTABLISHED 1935/sshd: user [pr 
	tcp        0      0 192.168.56.101:22       192.168.56.1:36344      ESTABLISHED 15920/sshd: user [p
```

{% capture notice %}
Выводы:
1. Команда ifconfig (ipconfig в Windows) показывает основные настройки установленных в системе сетевых адаптеров.
1. Утилита позволяет проверить соединение до хоста, указанного по IP или доменному имени.
1. Для диагностики сети можно пинговать собственно компьютер, шлюз, другой компьютер в сети, хост в интернете по IP а затем и по доменному имени.
1. Затем нужно попробовать пропинговать этот компьютер с другого из той же сети.
1. Утилита Netcat (команда nc) используется для открытия соединения с хостом к определенному порту, для сканирования или прослушивания портов.
1. Команда arp -n показывает все хосты в локальной сети.
1. Команда netstat показывает все активные сетевые соединения, она удобна для просмотра работающих серверов и открытых портов.
{% endcapture %}
<div class="notice--info">{{ notice | markdownify }}</div>

### Веб-сервер

#### Зачем нужна служба HTTP?

#### Как работает веб-сервер изнутри?

#### Какие веб-сервера самые популярные?

#### Как установить и настроить веб-сервер Apache2 в Linux?

```bash
sudo apt update
sudo apt install apache2
systemctl status apache2
systemctl start apache2
netstat -tlpn
curl 10.4.23.11 80
sudo ufw status
sudo ufw app list
sudo ufw allow 'Apache'
```

#### Как обеспечить безопасность веб-службы?

```bash
openssl req -new -x509 -days 30 -keyout server.key -out server.pem

sudo a2enmod ssl
sudo a2ensite default-ssl
cd /etc/apache2/sites-available/
sudo vim default-ssl.conf
```

#### Как настроить виртуальные хосты?

```bash
sudo mkdir /var/www/test.com
sudo chown -R $USER:$USER /var/www/test.com
sudo chmod -R 755 /var/www/test.com
sudo vim /var/www/test.com/index.html
sudo vim /etc/apache2/sites-available/test.com.conf
sudo a2ensite test.com.conf
sudo systemctl restart apache2
```

```html
<html>
    <head>
        <title>Welcome to test.com!</title>
    </head>
    <body>
        <h1>Success!  The test.com virtual host is working!</h1>
    </body>
</html>
```

```html
<VirtualHost *:80>
    ServerAdmin webmaster@localhost
    ServerName test.com
    ServerAlias www.test.com
    DocumentRoot /var/www/ytest.com
    ErrorLog ${APACHE_LOG_DIR}/error.log
    CustomLog ${APACHE_LOG_DIR}/access.log combined
</VirtualHost>
```

#### Как установить и настроить Nginx?

```bash
sudo apt update
sudo apt install nginx
sudo ufw app list
sudo ufw allow 'Nginx Full'
sudo ufw status
systemctl status nginx
```

```bash
sudo nano /etc/nginx/sites-available/test.com
```

```
server {
        listen 80;
        listen [::]:80;

        root /var/www/test.com/html;
        index index.html index.htm index.nginx-debian.html;

        server_name test.com www.test.com;

        location / {
                try_files $uri $uri/ =404;
        }
}
```

```bash
sudo ln -s /etc/nginx/sites-available/test.com /etc/nginx/sites-enabled/
sudo systemctl restart nginx
```

```
server {

    listen 443 ssl;
    listen 80;

    server_name test.com;
    ssl_certificate /etc/ssl/your_domain.crt;
    ssl_certificate_key /etc/ssl/your_domain.key;
    ssl_session_cache shared:SSL:10m;
	ssl_session_timeout 10m;
	keepalive_timeout 70;
	ssl_protocols TLSv1 TLSv1.1 TLSv1.2;
	ssl_prefer_server_ciphers on;
}
```

#### Как мониторить работу веб-сервера?

### FTP-сервер

#### Зачем нужна служба FTP?

#### Как устроен протокол FTP?

#### Как работает FTP-сервер изнутри?

#### Как установить FTP-сервер на Linux?

#### Как обеспечить безопасность FTP-сервера?

#### Как настроить права доступа к FTP-службе и ресурсам?


## -Разработка веб-приложений 

### Основы протокола HTTP

### Получение удаленных ресурсов

### Парсинг веб-страниц

### Создание интернет-роботов

### Работа с внешним API

### Простейший веб-сервер

### Создание веб-сервиса


## -Разработка клиент-серверных приложений

### Хранение данных и файлов пользователя на сервере

### Загрузка файлов от пользователя

### Обеспечение доступа к локальным файлам сервера

### Разграничение доступа

### Использование СУБД

### Преобразование файлов на лету

### Выполнение сценариев

### Толстый или тонкий клиент


## -Создание кроссплатформенного приложения

### Выбор платформы для сервера

### Клиент на Windows

### Клиент на \*nix

### Браузерный клиент

### Мобильный клиент

### Обеспечение омниканальности


## Архитектура сетевых приложений

### Монолитное веб-приложение

### Двухзвенное приложение

### Трехзвенное приложение

### Безсерверное приложение

### Микросервисная архитектура

### Облачные приложения


## -Разработка многопользовательских приложений

### Отслеживание разных пользователей

### Сохранение сессии

### Идентификация, аутентификация

### Хранение паролей и персональных данных

### Вопросы безопасности приложений


## Непрерывная интеграция приложений

### Жизненный цикл разработки приложения

### Автоматизированное тестирование 

### Тестовые среды и управление конфигурациями

### Контейнеризация приложений


## Развертывание сетевых приложений

### Подготовка сетевой инфраструктуры

### Контейнеризация сетевых приложений

### Деплой на выделенном сервере

### Деплой на облачном провайдере

### Мониторинг серверного приложения
