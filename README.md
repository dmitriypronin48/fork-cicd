# Домашнее задание к занятию "`Что такое DevOps. CI/CD`" - `Пронин Дмитрий Андреевич`

---

### Задание 1

###### Авторизация Zabbix
![Установка Zabbix](https://github.com/dmitriypronin48/fork-cicd/blob/main/img/z1-1.jpg)

###### Устновка postgresql
```
apt install postgress
```
После установки postgresql, потребовалось изменить настройку в /etc/postgresql/14/main/pg_hba.conf
Скорректировал настройку для локальных пользователей:
```
local   all             all                                     md5
```
и для внешних 
```
host    all             all             127.0.0.1/32            md5
host    zabbix          zabbix          192.168.0.249/32        md5

```


---

### Задание 2

###### Установка Zabbix agent
![Установка jenkins](https://github.com/dmitriypronin48/fork-cicd/blob/main/img/z2-3.jpg)


---



