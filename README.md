# ag_conf_web

# ТЗ к приложению.

- Логирование, пароль мин 8 символов.
- Меню:
    - отправка команд на приборы
    - просмотр статуса команд
    - создание dbf по списку
    - установка / снятие защиты БК
    - форматирование карт rfid
    - cоздание carslist ag/tkfc
    - список карт для внесения в АГ

## Отправка команд 

- внесение списка приборов в поле 1
- ввод списка команд в поле 2
- ссылка на конфиг pdf
- кнопка "отправить" отправляет команды
- "отмена", удаляет файлы уже размещённых команд.
- Создаёт запись в БД об отправке команды прибор/дата/время/команды

! отправка команд осыществляется по 100 шт с перерывом в 5 мин.

## Просмотр статуса команд

- таблица 
/№ бк / № прошивки / дата,время последнего конфигурирования /последний список команд / ответы БК
* экспорт csv
* сортировка, фильтрация по столбам

- раз в 2 минуты смотрит логи по бк по которым не закочена конфигурация и проверяет логи в поисках окончания конфигурирования либо ошибки. обновляет статусы и инфу в бд для вывода в таблицу.
* интерактивное обновление таблицы на основании обновления бд.

## Cоздание dbf по списку

- внесение списка приборов в поле 1
- парольэ в поле 2, если пустой то будет testtest
- кнопка создать
- возвращает zip архив с готовыми dbf

## Установка / снятие защиты БК

- внесение списка приборов в поле 1 с паролями через tab
- выбор конфигурации команд галочками.
    ! Вернуть команды архивом не размещаяя на сервере
    - номер телефона
    - текущий уровень защиты
    - снять защиту 1 уровня
    - поставить защиту 1 уровня
    - затереть домен
        - установить указаный
    - затереть ip
        - установить указаный
    - временно снять защиту
        - поле для ввода команд с временно снятой защитой
        - после команд из поля выходит из enterpass

## Форматирование карт rfid

    - поле ввода карт списком
    - выбор формата введёных карт
    - выбор формата в который перевести
    - кнопка перевести
    - поле с готовыми картами




