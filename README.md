# Домашнее задание к занятию "`Система мониторинга Zabbix. Часть 2`" - `Пронин Дмитрий Андреевич`

---

### Задание 1

###### Создайте свой шаблон, в котором будут элементы данных, мониторящие загрузку CPU и RAM хоста.


1. В веб-интерфейсе Zabbix Servera в разделе Templates создайте новый шаблон
![создание темплейта](https://github.com/dmitriypronin48/fork-cicd/blob/main/img/zz1-1.jpg)

2. Создайте Item который будет собирать информацию об загрузке CPU в процентах
3. Создайте Item который будет собирать информацию об загрузке RAM в процентах
![создание темплейта](https://github.com/dmitriypronin48/fork-cicd/blob/main/img/zz1-2-3.jpg)


---

### Задание 2

###### Добавьте в Zabbix два хоста и задайте им имена <фамилия и инициалы-1> и <фамилия и инициалы-2>. Например: ivanovii-1 и ivanovii-2.
Выполняя ДЗ сверяйтесь с процессом отражённым в записи лекции.
Установите Zabbix Agent на 2 виртмашины, одной из них может быть ваш Zabbix Server
Добавьте Zabbix Server в список разрешенных серверов ваших Zabbix Agentов
Добавьте Zabbix Agentов в раздел Configuration > Hosts вашего Zabbix Servera
Прикрепите за каждым хостом шаблон Linux by Zabbix Agent
Проверьте что в разделе Latest Data начали появляться данные с добавленных агентов

Данные действия выполнялись на прошлом занятии, менять не чего не стал, так как эти пункты уже сделаны.
Названия так же не стал менять машин, потому что мне так удобней в забиксе ориентироваться.
![создание темплейта](https://github.com/dmitriypronin48/fork-cicd/blob/main/img/zz2-1.jpg)
![создание темплейта](https://github.com/dmitriypronin48/fork-cicd/blob/main/img/zz2-2.jpg)



###### Добавляем Host в Zabbix
![Добавили первый хост](https://github.com/dmitriypronin48/fork-cicd/blob/main/img/z2-1.jpg)

![Добавили второй хост](https://github.com/dmitriypronin48/fork-cicd/blob/main/img/z2-2.jpg)

В настройках Zabbix agent скорректировал хост сервера

![Добавили второй хост](https://github.com/dmitriypronin48/fork-cicd/blob/main/img/z2-3.jpg)


![Добавили второй хост](https://github.com/dmitriypronin48/fork-cicd/blob/main/img/z2-4.jpg)

---



