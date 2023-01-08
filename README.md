### Создать БД 

## ``CREATE DATABASE; `` *`CREATE DATABASE test;`*

---

### SQL-команда, которая отвечает за просмотр доступных баз данных.

## ``SHOW DATABASES;`` 

---

### С помощью этой SQL-команды USE выбирается база данных, с которой хотим работать.

## ``USE;`` *`USE test;`*

---

### Стандартная SQL-команда для удаления БД.

## ``DROP DATABASE;`` 

---

### С помощью этой команды можно увидеть все таблицы.

## ``SHOW TABLES;`` 

---

### SQL-команда для создания новой таблицы.

## ``CREATE TABLE;`` 

### *``CREATE TABLE Persons (PersonID int, LastName varchar(255), Sity varchar(255), Phone int);``*


табл. Cont
|PersonID|Name     | Sity              | Phone |
|-| ------------- |:------------------:| -----:|
|_| _    | _  | _ |

*где ``int`` - числовое значение
``varchar`` - прописное

---

## Заполняем данными таблицу.

## ``insert into;``
Заполняем.

### *``insert into Cont (PersonID,Name,Sity,Phone) values (1,"Иван ", "Пермь ", 8 900 000 11 11 );``*
Получаем

табл. Cont
|PersonID|Name     | Sity              | Phone |
|-| ------------- |:------------------:| -----:|
|1| Иван    | Пермь   | 8 900 000 11 11 |




---

## Поиск по ключевому слову или числу. К примеру нам надо найти по телефону человека. Тут я уже пополнил таблицу.

табл. Cont
|PersonID|Name     | Sity              | Phone |
|-| ------------- |:------------------:| -----:|
|1| Иван    | Пермь   | 8 900 000 11 11 |
|2| Петр     | Москва |   8 900 00 11 52 |
|3| Инна  | Чебоксары        |     852 45 45 |

## ``select * from <<Таблица>> where <<столбец>> = <<"Значение">>;`` 

Разбор 

### *``select * from Cont where phone = "852 45 45";``*

Результат 

|PersonID|Name     | Sity              | Phone |
|-| ------------- |:------------------:| -----:|
|3| Инна  | Чебоксары        |     852 45 45 |

---

### Например нам надо узнать сколько полетов совершила Инна за месяц.

## ``SELECT COUNT(*) AS count FROM <<таблица>> WHERE <<Столбец>> = <<'Значение'>> ``

табл. trip
|PersonID|Name     | plane             | sity |
|-| ------------- |:------------------:| -----:|
|1| Иван    | Boeing  | Ростов |
|2| Петр     | Boeing | Омск |
|3| Инна  | IL-86        |  Архангельск  |
|4| Инна  | IL-86        | Чебоксары |
|5| Петр     | Boeing | Москва   |

Разбор 

### *``SELECT COUNT(*) AS count FROM trip WHERE name = 'Инна' ``*

|Count    |  
| ------------- |
|2 |

---

### Добавление новых данных в таблицу

 ## ``insert into;`` 

Например мы Добавить Игорь из Саратова без номера телефона

табл. Cont
PersonID|Name     | Sity              | Phone |
|-| ------------- |:------------------:| -----:|
|1| Иван    | Пермь   | 8 900 000 11 11 |
|2| Петр     | Москва |   8 900 00 11 52 |
|3| Инна  | Чебоксары        |     852 45 45 |

Разбор
### *``insert into Cont (PersonID,Name,Sity,Phone) values (4,"Игорь", "Саратов", NULL );``*

табл. Cont
PersonID|Name     | Sity              | Phone |
|-| ------------- |:------------------:| -----:|
|1| Иван    | Пермь   | 8 900 000 11 11 |
|2| Петр     | Москва |   8 900 00 11 52 |
|3| Инна  | Чебоксары        |     852 45 45 |
|4| Игорь  | Саратов       |  NULL |

---

## Изменение данных в таблице.
 ### ``UPDATE <<таблица>> SET <<столбец где хотим внести изменения>> = <<значение>> WHERE <<ключ где будем менять>>;`` 

К примеру мы узнали телефон Игоря 8 999 852 54 54

табл. Cont
PersonID|Name     | Sity              | Phone |
|-| ------------- |:------------------:| -----:|
|1| Иван    | Пермь   | 8 900 000 11 11 |
|2| Петр     | Москва |   8 900 00 11 52 |
|3| Инна  | Чебоксары        |     852 45 45 |
|4| Игорь  | Саратов       |  NULL |

разбор

*``UPDATE cont SET phone= 8 999 852 54 54 WHERE PersonID = 4;``*

табл. Cont
PersonID|Name     | Sity              | Phone |
|-| ------------- |:------------------:| -----:|
|1| Иван    | Пермь   | 8 900 000 11 11 |
|2| Петр     | Москва |   8 900 00 11 52 |
|3| Инна  | Чебоксары        |     852 45 45 |
|4| Игорь  | Саратов       |  8 999 852 54 54 |


---


