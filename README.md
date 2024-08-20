# Домашнее задание к занятию "`Система мониторинга Zabbix`" - `Пронин Дмитрий Андреевич`

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
Для того чтобы пользователи могли подключаться не только по localhost, потребовалось скорректировать настройки в /etc/postgresql/14/main/postgresql.conf:
```
listen_addresses = '*'
```
###### Устновка Zabbix
Ориентировался на сборку вот такую https://www.zabbix.com/ru/download?zabbix=6.4&os_distribution=ubuntu&os_version=22.04&components=server_frontend_agent&db=pgsql&ws=apache
```
wget https://repo.zabbix.com/zabbix/6.4/ubuntu/pool/main/z/zabbix-release/zabbix-release_6.4-1+ubuntu22.04_all.deb   - выкачиваем deb пакет для репозиториев
dpkg -i zabbix-release_6.4-1+ubuntu22.04_all.deb - добавляем репозитории
apt update - обновляем кеш
```
Далее приступаем к самой установке.
```
apt install zabbix-server-pgsql zabbix-frontend-php php8.1-pgsql zabbix-apache-conf zabbix-sql-scripts
```
Но есть одно но, php8.1-pgsql очень плохо работает с версией php 8.3.10, об этом я уже узнал после установки.
Пришлось удалять 
```
apt remove --purge php8.1-pgsql
apt autoremove
```
Далее делаем еще раз установку компонента
```
apt update && apt install php8.3-pgsql
```
###### Пришла очередь поработать с БД.
Заходим в оболочку БД.
```
su - postgres
```
Требуется провалиться в psql.
![Оболочка БД](https://github.com/dmitriypronin48/fork-cicd/blob/main/img/z1-2.jpg)

Тут уже я применил ряд комманд:
```
CREATE DATABASE zabbix; - создал БД
CREATE USER zabbix WITH LOGIN PASSWORD '123456789'; -создание юзера для бд
GRANT ALL PRIVILEGES ON DATABASE zabbix TO zabbix; - права для бд
ALTER DATABASE zabbix OWNER TO zabbix; - назначение владельца бд
ALTER ROLE zabbix WITH LOGIN; - создание роли к бд
GRANT CONNECT ON DATABASE zabbix TO zabbix; - создание подключения к бд
```





---

### Задание 2

###### Установка Zabbix agent
![Установка jenkins](https://github.com/dmitriypronin48/fork-cicd/blob/main/img/z2-3.jpg)


---



