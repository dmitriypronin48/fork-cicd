# Домашнее задание к занятию «Работа с данными (DDL/DML)» - `Пронин Дмитрий Андреевич`

---

### Задание 1
1.1. Поднимите чистый инстанс MySQL версии 8.0+. Можно использовать локальный сервер или контейнер Docker.

1.2. Создайте учётную запись sys_temp.
```
CREATE USER 'sys_temp'@'%' IDENTIFIED BY 'qwerty99';
```

1.3. Выполните запрос на получение списка пользователей в базе данных. 
```
SELECT User, Host FROM mysql.user;
```
![скрин](https://github.com/dmitriypronin48/fork-cicd/blob/main/img/z1-1.jpg)

1.4. Дайте все права для пользователя sys_temp.
```
GRANT ALL PRIVILEGES ON *.* TO 'sys_temp'@'%';
```
![скрин](https://github.com/dmitriypronin48/fork-cicd/blob/main/img/z1-2.jpg)

1.5. Выполните запрос на получение списка прав для пользователя sys_temp. (скриншот)
```
SHOW GRANTS FOR sys_temp;
```
![скрин](https://github.com/dmitriypronin48/fork-cicd/blob/main/img/z1-3.jpg)
1.6. Переподключитесь к базе данных от имени sys_temp.

Для смены типа аутентификации с sha2 используйте запрос:
```
ALTER USER 'sys_temp'@'%' IDENTIFIED WITH mysql_native_password BY 'qwerty99';
```

![скрин](https://github.com/dmitriypronin48/fork-cicd/blob/main/img/z1-6.jpg)

1.6. По ссылке https://downloads.mysql.com/docs/sakila-db.zip скачайте дамп базы данных.
```
wget https://downloads.mysql.com/docs/sakila-db.zip скачайте дамп базы данных

```

1.7. Восстановите дамп в базу данных.
```
Изначально подрубился к бд и сделал там CREATE DATABASE sakila;
mysql -u sys_temp -p sakila < sakila-schema.sql
mysql -u sys_temp -p sakila < sakila-data.sql
```
1.8. При работе в IDE сформируйте ER-диаграмму получившейся базы данных. При работе в командной строке используйте команду для получения всех таблиц базы данных. (скриншот)

Результатом работы должны быть скриншоты обозначенных заданий, а также простыня со всеми запросами.

![скрин](https://github.com/dmitriypronin48/fork-cicd/blob/main/img/z1-7.jpg)

---

### Задание 2
Составьте таблицу, используя любой текстовый редактор или Excel, в которой должно быть два столбца: в первом должны быть названия таблиц восстановленной базы, во втором названия первичных ключей этих таблиц. Пример: (скриншот/текст)

```
Название таблицы | Название первичного ключа
customer         | customer_id
```

```
mysql> SELECT
    ->     kcu.TABLE_NAME,
    ->     kcu.COLUMN_NAME,
    ->     tc.CONSTRAINT_NAME AS PRIMARY_KEY_NAME
    -> FROM
    ->     INFORMATION_SCHEMA.KEY_COLUMN_USAGE AS kcu
    -> JOIN
    ->     INFORMATION_SCHEMA.TABLE_CONSTRAINTS AS tc
    ->     ON kcu.TABLE_NAME = tc.TABLE_NAME
    ->     AND kcu.TABLE_SCHEMA = tc.TABLE_SCHEMA
    ->     AND kcu.CONSTRAINT_NAME = tc.CONSTRAINT_NAME
    -> WHERE
    ->     kcu.TABLE_SCHEMA = 'sakila'
    ->     AND tc.CONSTRAINT_TYPE = 'PRIMARY KEY';
+---------------+--------------+------------------+
| TABLE_NAME    | COLUMN_NAME  | PRIMARY_KEY_NAME |
+---------------+--------------+------------------+
| actor         | actor_id     | PRIMARY          |
| address       | address_id   | PRIMARY          |
| category      | category_id  | PRIMARY          |
| city          | city_id      | PRIMARY          |
| country       | country_id   | PRIMARY          |
| customer      | customer_id  | PRIMARY          |
| film          | film_id      | PRIMARY          |
| film_actor    | actor_id     | PRIMARY          |
| film_actor    | film_id      | PRIMARY          |
| film_category | film_id      | PRIMARY          |
| film_category | category_id  | PRIMARY          |
| film_text     | film_id      | PRIMARY          |
| inventory     | inventory_id | PRIMARY          |
| language      | language_id  | PRIMARY          |
| payment       | payment_id   | PRIMARY          |
| rental        | rental_id    | PRIMARY          |
| staff         | staff_id     | PRIMARY          |
| store         | store_id     | PRIMARY          |
+---------------+--------------+------------------+
```




