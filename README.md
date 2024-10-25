# Домашнее задание к занятию «Кеширование Redis/memcached» - `Пронин Дмитрий Андреевич`

---

### Задание 1
Задание 1. Кеширование
Приведите примеры проблем, которые может решить кеширование.

```
ответ:  Например приложение запрашивает данные (например, из базы данных или через интернет, не важно), это может занять некоторое время. Если эти данные запрашиваются часто, их можно сохранить в кэше, который находится ближе приложению. Таким образом, в следующий раз, когда потребуется та же информация, приложение сможет получить её быстрее, не обращаясь к исходному месту хранения. Проще говоря информация храниться в памяти и пользователь или разработчик тот же, получил информацию из источника быстрее.
```

---

### Задание 2

Задание 2. Memcached
Установите и запустите memcached.

Приведите скриншот systemctl status memcached, где будет видно, что memcached запущен.

![скрин](https://github.com/dmitriypronin48/fork-cicd/blob/main/img/z2-1.jpg)



---

### Задание 3. Удаление по TTL в Memcached
Запишите в memcached несколько ключей с любыми именами и значениями, для которых выставлен TTL 5.

Приведите скриншот, на котором видно, что спустя 5 секунд ключи удалились из базы.



---

### Задание 4. Запись данных в Redis
Запишите в Redis несколько ключей с любыми именами и значениями.

Через redis-cli достаньте все записанные ключи и значения из базы, приведите скриншот этой операции.


---

![скрин](https://github.com/dmitriypronin48/fork-cicd/blob/main/img/z2-2.jpg)
