# Автозаполнение для поля ввода города

Программный интерфейс возвращает список городов, соответствующий поисковому запросу, и предназначен, в частности, для автозаполнения в полях ввода города.

## Адреса сервиса

    1. HTTP: http://w7.tks.ru:5001/
    2. HTTPS: https://w7.tks.ru:5002/

## Запросы

    <адрес сервиса>?term=<поисковый запрос>&mode=[from|to]

## Режимы

1. **mode=from** - поиск по таблице, полученной из базы Cities500 GeoNames, содержит города мира населённостью более 500 человек. Возможно использование латиницы.
2. **mode=to** - поиск по базе ФИАС, урезанный до городов

## Результат

Сервис возвращает список найденных населённых пунктов.

## Примеры

https://w7.tks.ru:5002/?term=шан&mode=from

вернёт результат:

    [ 
      "Шанхай (Shanghai), Китай", 
      "Шантоу (Shantou), Китай", 
      "Шанъюй (Shangyu), Китай", 
      "Шангжао (Shangrao), Китай", 
      "Шанцю (Shangqiu), Китай", 
      "Шаньвэй (Shanwei), Китай", 
      "Шаньхайгуань (Shanhaiguan), Китай", 
      "Шангри-Ла (Shangri-La), Китай", 
      "Шани (Shawnee), Соединенные Штаты", 
      "Шантили (Chantilly), Соединенные Штаты", 
      "Шанвйер си Марн (Chennevieres-sur-Marne), Франция", 
      "Шаннон (Shannon), Ирландия", 
      "Шантелу-ле-Винь (Chanteloup-les-Vignes), Франция", 
      "Шанут (Chanute), Соединенные Штаты", 
      "Шантоне (Chantonnay), Франция", 
      "Касл Шанон (Castle Shannon), Соединенные Штаты", 
      "Шанклин (Shanklin), Соединенное Королевство", 
      "Шантепи (Chantepie), Франция", 
      "Шантобе (Shantobe), Казахстан", 
      "Бру сир Шантрен (Brou-sur-Chantereine), Франция" 
    ]


https://w7.tks.ru:5002/?term=ме&mode=to

вернёт результат:

    [ 
      "АО Ханты-Мансийский Автономный округ - Югра, г Мегион", 
      "обл Калужская, р-н Медынский, г Медынь", 
      "Респ Башкортостан, р-н Мелеузовский, г Мелеуз", 
      "обл Архангельская, р-н Мезенский, г Мезень", 
      "обл Калужская, р-н Мещовский, г Мещовск", 
      "обл Владимирская, р-н Меленковский, г Меленки", 
      "Респ Башкортостан, г Межгорье", 
      "Респ Татарстан, р-н Мензелинский, г Мензелинск", 
      "обл Оренбургская, г Медногорск", 
      "Респ Татарстан, р-н Менделеевский, г Менделеевск", 
      "обл Кемеровская, г Междуреченск", 
      "Респ Карелия, р-н Медвежьегорский, г Медвежьегорск" 
    ]

## Демо

Демонстрационный сервис, реализованный с использованием библиотеки jQuery:

https://w7.tks.ru:5002/static/demo_cities_ajax.html

## Примечания

Предполагается, что для поля, в котором предполагается указание зарубежного города, используется режим **mode=from**, а для поля, в котором предполагается российский город - режим **mode=to**.
