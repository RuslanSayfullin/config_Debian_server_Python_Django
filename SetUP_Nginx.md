разработка Sayfullin RR
========================================================================================================================

// Руководство //
Первоначальная настройка NGINX

Установка на компьютер с Debian
========================================================================================================================
Вам необходимо установить NGINX с открытым исходным кодом на машине с Debian:

Создайте файл с именем /etc/apt/sources.list.d/nginx.list следующего содержания:
    deb http://nginx.org/packages/mainline/debian/ CODENAME nginx
    deb-src http://nginx.org/packages/mainline/debian/ CODENAME nginx
    * Измените файл, слово CODENAME на кодовое имя вашего дистрибутива: bullseye, jessie или stretch, если это Debian.

Затем выполните приведенные ниже команды:
    $ wget http://nginx.org/keys/nginx_signing.key
    $ sudo apt-key add nginx_signing.key
    $ sudo apt-get update
    $ sudo apt-get install -y nginx
    $ sudo /etc/init.d/nginx start

Проверка установки:
    $ sudo nginx -v
    $ sudo ps -ef | grep nginx

Чтобы убедиться, что NGINX возвращает запросы правильно, используйте свой браузер и отправьте запрос на ваш компьютер 
или воспользуйтесь командой curl :
    $ sudo curl localhost
    *Вы увидите страницу приветствия NGINX.

Команды NGINX
$ sudo nginx -h :Показывает справочное меню NGINX.
$ sudo nginx -v :Показывает версию NGINX.
$ sudo nginx -V :Показывает версию NGINX, информацию о сборке и аргументы конфигурации, где даны модули, встроенные в двоичный файл NGINX.
$ sudo nginx -t :Проверяет конфигурацию NGINX.
$ sudo nginx -T :Проверяет конфигурацию NGINX и выводит ее проверенной на экран.
$ sudo nginx -s signal :Флаг -s отправляет сигнал главному процессу NGINX.

