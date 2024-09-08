# Домашнее задание к занятию "`Система мониторинга Zabbix. Часть 2`" - `Пронин Дмитрий Андреевич`

---

### Задание 1

###### Авторизация Zabbix















---

### Задание 2

###### Установка Zabbix agent
```
wget https://repo.zabbix.com/zabbix/6.4/ubuntu/pool/main/z/zabbix-release/zabbix-release_6.4-1+ubuntu22.04_all.deb   - выкачиваем deb пакет для репозиториев
dpkg -i zabbix-release_6.4-1+ubuntu22.04_all.deb - добавляем репозитории
apt update - обновляем кеш
apt install zabbix-agent
```
###### Добавляем Host в Zabbix
![Добавили первый хост](https://github.com/dmitriypronin48/fork-cicd/blob/main/img/z2-1.jpg)

![Добавили второй хост](https://github.com/dmitriypronin48/fork-cicd/blob/main/img/z2-2.jpg)

В настройках Zabbix agent скорректировал хост сервера

![Добавили второй хост](https://github.com/dmitriypronin48/fork-cicd/blob/main/img/z2-3.jpg)


![Добавили второй хост](https://github.com/dmitriypronin48/fork-cicd/blob/main/img/z2-4.jpg)

---



