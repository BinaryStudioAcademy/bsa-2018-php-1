Binary Studio Academy PHP 2018
====

### Домашнее задание #1

#### Требования

Внимание: До начала выполнения задания следует убедиться, что у вас настроено рабочее окружение.
А именно:
 - php7.2
 - git
 - composer

Рекомендуется использовать Vagrant и виртуальную машину Homestead.
Подробнее здесь: https://laravel.com/docs/5.6/homestead

***

#### Установка

Установка показана в рабочем окружении OS Linux:

```bash
git clone git@github.com:BinaryStudioAcademy/bsa-2018-php-1.git
cd bsa-2018-php-1
composer install
```

#### Структура заданий

Все задания разделены по папкам внутри `/src`.

Вашей задачей, в большинтсве случаев, будет дополнить существующий код недостающей
функциональностью.
Набор данных для каждого задания будет жёстко задан с целью проверки в тестах.

***

#### Задание 1

В первом задании (Task1) необходимо работать с перспективным рынком криптовалют.

Вам необходимо создать несколько криптовалют опираясь на интерфейс `Currency` и используя данные из таблицы.

| Name      | Logo
|-----------|--------------------------------------------------------------|
| Bitcoin   | https://s2.coinmarketcap.com/static/img/coins/32x32/1.png    |
| Ethereum  | https://s2.coinmarketcap.com/static/img/coins/32x32/1027.png |
| Dogecoin  | https://s2.coinmarketcap.com/static/img/coins/32x32/74.png   |

Также необходимо реализовать метод `getDailyPrice` в каждом екземпляре класса криптовалюты. При создании валюты 
указывается ее цена.

Далее вам необходимо работать с классом `CoinMarket`, реализовав методы `addCurrency`, `getCurrencies`, `maxPrice`.

Проверить себя можно запустив:
```bash
./vendor/bin/phpunit --testsuite task1
```

***

#### Задание 2

Во втором задании (Task2) нужно реализовать простой генератор (используя `yield`), который возвращает следующие emoji:

'🚀', '🚃', '🚄', '🚅', '🚇'.

Для этого нужно реализовать метод `generate` в классе `EmojiGenerator`.

Проверить себя можно запустив:
```bash
./vendor/bin/phpunit --testsuite task2
```

***

#### Задание 3

В третьем задании (Task 3) мы будем практиковаться со встроенным web-сервером php.
Ваша задача состоит в том, чтобы отрендерить список созданных вами в задании 1 криптовалют и отобразить страницу,
используя встроенный web-сервер.

Для этого вам необходимо наполнить рынок криптовалютами в файле `index.php` и реализовать метод `present` класса 
`MarketHtmlPresenter`, опираясь на код тестов к заданию.

Если вы используете Homestead, то для начала нужно остановить `nginx`.

```shell
sudo pkill nginx
```
Затем запустить встроенный веб-сервер:

```
php -S 0.0.0.0:80 -t ./src/Task3
```
Мoжет потребоваться команда "sudo php -S 0.0.0.0:80 -t ./src/Task3".

Страница будет доступна в браузере по адресу:  

[http://192.168.10.10:80](http://192.168.10.10:80) - если используете homestead

[http://127.0.0.1:80](http://127.0.0.1:80) - если запускаете с локальной машины

Часть кода уже содержится в файле `index.php`. 

Проверить себя можно запустив:
```bash
./vendor/bin/phpunit --testsuite task3
```

***

#### Проверка

Вы уже, наверное, заметили, что для проверки заданий мы используем [PHPUnit](https://phpunit.de/getting-started.html).
Это необходимо для того, чтобы проверить соответсвуют ли ваши решения нашим ожиданиям (предложенной спецификации).
Если вы ранее не знакомы с PHPUnit, то не расстраивайтесь. Мы рассмотрим его в дальнейших лекциях более подробно.

На данном этапе можете считать, что лишь автопроверка (как на [codewars.com](https://www.codewars.com))

В начале все тесты "красные", т.е. поломанные. Для того чтобы они стали рабочими (зелёными) и не было ошибок,
вам необходимо реализовать необходимые решения.

**Какой профит от тестов?**

* **Для вас**: Уверенность, что вы на правильном пути. (В тестах ну ооочень много подсказок)
* **Для нас**: Рутинная проверка сводится к минимуму, и мы сможем сосредоточится на рекомендациях и фидбеке.

**Чего делать не стоит**
* Менять код assert-ов в тестах
* Тупо подгонять ответы под ожидаемые результаты.(Код мы все равно будем смотреть)


Запуск всех тестов:

```bash
./vendor/bin/phpunit
```

Запуск теста для конкретного задания:

```bash
./vendor/bin/phpunit --testsuite task1
```

#### Приём решений

В идеале необходимо разместить ваше решение в отдельном репозитории на Github или Bitbucket
и прислать ссылку на него.

Задавайте вопросы в комментариях к заданию в случае возникновения проблем.
