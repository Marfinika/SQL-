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

## ``CREATE TABLE Persons (PersonID int, LastName varchar(255), Sity varchar(255), Phone int);``
где ``int`` - числовое значение
``varchar`` - прописное

---

### Поиск по ключевому слову или числу. К примеру нам надо найти по телефону человека.

табл. Cont
|Name     | Sity              | Phone |
| ------------- |:------------------:| -----:|
| Иван    | Пермь   | 8 900 000 11 11 |
| Петр     | Москва |   8 900 00 11 52 |
| Инна  | Чебоксары        |     852 45 45 |

## ``select * from <<Таблица>> where <<столбец>> = <<"Значение">>;`` 

Разбор 

### ``select * from Cont where phone = "852 45 45";``

Результат 

|Name     | Sity              | Phone |
| ------------- |:------------------:| -----:|
| Инна  | Чебоксары        |     852 45 45 |

---

### Например нам надо узнать сколько полетов совершила Инна за месяц.

## ``SELECT COUNT(*) AS count FROM <<таблица>> WHERE <<Столбец>> = <<'Значение'>> ``

табл. trip
|Name     | plane             | sity |
| ------------- |:------------------:| -----:|
| Иван    | Boeing  | Ростов |
| Петр     | Boeing | Омск |
| Инна  | IL-86        |  Архангельск  |
| Инна  | IL-86        | Чебоксары |
| Петр     | Boeing | Москва   |

Разбор 

## ``SELECT COUNT(*) AS count FROM trip WHERE name = 'Инна' ``

|Count    |  
| ------------- |
|2 |

---

### Добавление новых данных в таблицу

 ## ``insert into;`` 

Например мы Добавить Игорь из Саратова без номера телефона

табл. Cont
|Name     | Sity              | Phone |
| ------------- |:------------------:| -----:|
| Иван    | Пермь   | 8 900 000 11 11 |
| Петр     | Москва |   8 900 00 11 52 |
| Инна  | Чебоксары        |     852 45 45 |

Разбор
## ``insert into Cont (Name,Sity,Phone) values ("Игорь", "Саратов", NULL );``

|Name     | Sity              | Phone |
| ------------- |:------------------:| -----:|
| Иван    | Пермь   | 8 900 000 11 11 |
| Петр     | Москва |   8 900 00 11 52 |
| Инна  | Чебоксары        |     852 45 45 |
| Игорь  | Саратов       |  NULL |

---

### Изменение данных в таблице.
 ## ``UPDATE <<таблица>> SET <<столбец где хотим внести изменения>> = <<значение>> WHERE <<ключ где будем менять>>;`` 

К примеру мы узнали телефон Игоря 8 999 852 54 54

табл. Cont
|Name     | Sity              | Phone |
| ------------- |:------------------:| -----:|
| Иван    | Пермь   | 8 900 000 11 11 |
| Петр     | Москва |   8 900 00 11 52 |
| Инна  | Чебоксары        |     852 45 45 |
| Игорь  | Саратов       |  NULL |

разбор

UPDATE cont SET phone= 8 999 852 54 54 WHERE name = "Игорь";

|Name     | Sity              | Phone |
| ------------- |:------------------:| -----:|
| Иван    | Пермь   | 8 900 000 11 11 |
| Петр     | Москва |   8 900 00 11 52 |
| Инна  | Чебоксары        |     852 45 45 |
| Игорь  | Саратов       | 8 999 852 54 54 |

```__Лучше изначально создавать уникальное id, что бы не искать по name__```

---


