## Оглавление

* [SWbot](#swbot)
* [Цена](#Цена)
* [Требования к серверу](#Требования-к-серверу)
* [Ошибки программы](#Ошибки-программы)
* [Образец конфига](#Образец-конфига)
  * [Образец Глобального конфига для начинающего пользователя](#Образец-Глобального-конфига-для-начинающего-пользователя)
* [Стратегии](#Стратегии)
  * [Стратегия работы по индикаторам](#Стратегия-работы-по-индикаторам)
  * [Стратегия усреднения Short (накапливаем вторую монету в паре)](#Стратегия-усреднения-short-накапливаем-вторую-монету-в-паре)
  * [Стратегия усреднения Long (Накапливает первую монету в паре)](#Стратегия-усреднения-long-Накапливает-первую-монету-в-паре)
  * [Стратегия "Работа по сигналам"](#Стратегия-Работа-по-сигналам)
  * [Стратегия "Работа по внешним сигналам"](#Стратегия-Работа-по-внешним-сигналам)
* [Сетка "Hold percentage" и "Мартингейл"](#Сетка-hold-percentage-и-Мартингейл)
* [Кто запускал конфиги, скажите есть профит?](#Кто-запускал-конфиги-скажите-есть-профит)
* [Кто может научить настраивать SWbot](#Кто-может-научить-настраивать-swbot)
* [Сводная информация по всем ботам, биржам и данному проекту "Крипто глупости"](/README.md)

# SWbot

Терминальный бот с полноценной возможностью управления через web-панель, встроенным визуальным графиком курсов валют и возможностью торговли на множестве пар. Умеет торговать по индикаторам, трейл на закуп и на продажу, торговля по встроенным сигналам.

* [Официальный сайт бота SWbot](http://swbot.info)
* [Официальный FAQ SWbot](http://swbot.info/faq)
* [Телеграм-канал технической поддержки Gbota](https://t.me/Smart_bot_alfa)
* [Видео-уроки по использованию SWbot](https://www.youtube.com/watch?v=ol7kUz-SLmc&list=PLbYtQ6_YnkBRwVXGr9sxdJrwSLIp6pIoz)
* Реферальный код при покупке SWbot: http://swbot.info/signup?ref=99 или реферальный код 99. Укажите и это поможет поддержать проект "Крипто глупости" и переодически мотивировать нас, выкладывать свежие конфиги. Заранее спасибо!
* [Сравнительная таблица по ботам](https://docs.google.com/spreadsheets/d/1VMG21PQHvU3cDLZ6fLL17TWjiEgWzSpRfk3jA37MMUg/edit?usp=sharing) где SWbot занимает одну из лидирующих позиций. Рекомендуем к применению новичкам.


## Цена

Бот стоит 25$ в месяц аренды на одну биржу, но есть демо-режим, который полностью функциональный и ограничивает вас суммой торговли 0.025 BTC, на текущий момент времени это ~ 400 $.

Еще одно ограничение демо-режима, бот торгует только в тех парах где есть BTC, например USDT-BTC, LTC-BTC, ETH-BTC, а вот в парах USDT-LTC или LTC-ETH бот в демо-режиме торговать не будет. При этом допускается торговля на одной бирже и не больше двух валютных пар.

## Требования к серверу

Бот терминальный и не требует много ресурсов, хватит самого дешевого сервера с тарифным планом ~5$ в месяц, либо домашнего компьютера, который вы готовы оставить работать круглосуточно. Рекомендуемые требования к компьютеру от разработчиков программы:

* Процессор i3 2.3Ghz или выше
* Оперативная память 100mb
* Место на диске 50mb

## Ошибки программы

Ситуаций, когда SWbot закрывается с ошибкой не встречались, но так как проект молодой и частые обновления, переодически устаревшие версии перестают работать. Обновляйтесь до актуальной версии.

## Образец конфига

Образцы конфига выложены в папке бота. Если вы мечтаете скачать конфиг, запустить его, а утром проснуться с доходом +100500 денег, то вынуждены разочаровать. Такого конфига нет и никогда не будет, можно сформировать конфиг на довольно долгосрочную работу, но его доходность будет находится в пределах +5% в месяц. В любом случае потребуется ваше ежедневное участие в работе бота и его контроль и корректировка работы. Мы не рекомендуем запускать такой конфиг, так как он может вместо прибыли принести убытки.

У SWbot есть два понятния:
* Глобальный конфиг
* Локальный конфиг

Глобальный конфиг  - это текстовый файл в формате json, который расположен в той же папке, что и программа. Редактируется через "блокнот", но удобней через notepad++.

Локальный конфиг - настройка для каждой конкретной пары, редактируется через веб-панель. При добавлении пары в торги настройки берутся из Глобального конфига, дальше вы можете оставить как есть, либо провести корректировку. При удалении валютной пары из торгов, Локальный конфиг не сохраняется.

## Образец Глобального конфига для начинающего пользователя

Полностью автоматизирован, все настройки "подтягивает" самостоятельно, вам нужно вписать API ключи и при желании подключить телеграм-бота для получения уведомлений о торгах.

Файл должен быть размещен в той же директории, что и файл бота.

[Образец глобального конфига для начинающего пользователя](/configs/swbot/config.json). Внимание! Файл нужно отредактировать в блокноте или notepad++.

## Стратегии

### Стратегия работы по индикаторам

Бот позволяет использовать индикаторы: Линии Боллинджера и RSI. Индикаторы служат сигналом либо для открытия торгов и выставления профитного ордера, либо и для того и другого. Так же индикаторы совместимы с сеткой, трейлом и другими настройками. Стратегия учитывает минимальный профит, поэтому будет торговать только в плюс.

[Образец json файла](/configs/swbot/indicators.json) для стратегии работы по индикаторам. Внимание! Перед использованием удалите комментарии и исправьте параметры конфига.

### Стратегия усреднения Short (накапливаем вторую монету в паре)

Применима, когда вы открыли торги в Long, все ордера на закуп сработали, а курс ушел значительно ниже и возвращаться в ближайшее время не планируется. Например, в паре BTC/LTC вы купили LTC на все деньги, ждать момента, когда вы сможете продать LTC с профитом нужно очень много, открывается стратегия Short, которая позволит торговать в это же паре и накопить LTC в большем количестве, чем есть на текущий момент времени. Когда курс LTC возвращается к профитному ордеру Long, весь набранный объем LTC продаётся руками или возвращается стратегия Long.

[Образец json файла](/configs/swbot/short.json) для стратегии Short. Внимание! Перед использованием удалите комментарии и исправьте параметры конфига.

### Стратегия усреднения Long (Накапливает первую монету в паре)

Большая часть начинающих трейдеров не торгуют на падающем рынке, но нет ничего более доходного, чем падающий рынок. Как раз для это ситуации реализована данная стратегия, бот выставляет много ордеров вниз от текущей цены, тем самым скупая монеты при падении по самой выгодной цене, а затем когда курс возвращается на уровень начала падения - продаёт одним ордером всё закупленное.

[Образец json файла](/configs/swbot/long.json) для стратегии Short. Внимание! Перед использованием удалите комментарии и исправьте параметры конфига.

### Стратегия "Работа по сигналам"
Бот умеет торговать по «сигналам», которые ему поступают от внутренней системы аналитики или от внешнего источника. Дополнительная плата со стороны разработчика за данный сервис не взимается. 

[Образец json файла](/configs/swbot/signals.json) для стратегии Short. Внимание! Перед использованием удалите комментарии и исправьте параметры конфига.

### Стратегия "Работа по внешним сигналам"
Ничем не отличается от «Смарт торгов», в конфиг добавляется ссылка на страницу где выкладываются сигналы.
"analitic_url":"http://kassa-internet.com/analitic/650C0A353AD645DFA706E643F8208151", например, так. 

В данном случае встроенная аналитика Свбота не будет работать и сигналы боту предоставляются внешним источником. Вы можете самостоятельно организовать веб-страницу, на которую выкладываются названия пар, в которых должен торговать бот.

Сигналы вы можете получать из телеграм-каналов, памп-групп, новостных парталов или написать свою аналитику.


### Сетка "Hold percentage" и "Мартингейл"
По сути сводится к выставлению ордера с заданным шагом на закуп при падении курса. Задавая параметр в процентах, вы не ограничиваете себя количеством выставляемы ордеров, как в «сетке», а говорите, что бот должен закупаться каждый раз, когда курс упадёт на заданный процент.

Параметр может работать совместно с трейлом.

[Образец json файла](/configs/swbot/hp.json) для стратегии Short. Внимание! Перед использованием удалите комментарии и исправьте параметры конфига.

###  Кто запускал конфиги, скажите есть профит?

Профит есть, но важно понимать, что конфиги выложенные на данном сайте, в группе “Крипто глупости” формировались под конкретную ситуацию на рынке и на непродолжительное время. Не каждый конфиг из этой группы можно запустить в любой момент времени и ждать дохода. Для начала изучите бота и его стратегии, если тратить время на это жалко, то [приходите на тренинг](https://www.buh-seminar.ru/), мы всему научим в сжатые сроки.

## Кто может научить настраивать SWbot

В рамках проекта "Крипто глупости" каждого 15-го числа месяца запускается трениннг "Автоматическая и ручная торговля на крипто бирже". [Узнайте о нём подробней](/README.md#Обучение).
