# Домашнее задание к занятию «ELK» - `Пронин Дмитрий Андреевич`

---

### Задание 1
Задание 1. Elasticsearch
Установите и запустите Elasticsearch, после чего поменяйте параметр cluster_name на случайный.

Приведите скриншот команды 'curl -X GET 'localhost:9200/_cluster/health?pretty', сделанной на сервере с установленным Elasticsearch. Где будет виден нестандартный cluster_name.


![скрин](https://github.com/dmitriypronin48/fork-cicd/blob/main/img/z1-1.jpg)


---

### Задание 2

Задание 2. Kibana
Установите и запустите Kibana.

Приведите скриншот интерфейса Kibana на странице http://<ip вашего сервера>:5601/app/dev_tools#/console, где будет выполнен запрос GET /_cluster/health?pretty.

![скрин](https://github.com/dmitriypronin48/fork-cicd/blob/main/img/z2-1.jpg)
---

### Задание 3
Задание 3. Logstash
Установите и запустите Logstash и Nginx. С помощью Logstash отправьте access-лог Nginx в Elasticsearch.

Приведите скриншот интерфейса Kibana, на котором видны логи Nginx.

![скрин](https://github.com/dmitriypronin48/fork-cicd/blob/main/img/z3-1.jpg)
![скрин](https://github.com/dmitriypronin48/fork-cicd/blob/main/img/z3-2.jpg)

---

### Задание 4
Задание 4. Filebeat.
Установите и запустите Filebeat. Переключите поставку логов Nginx с Logstash на Filebeat.

Приведите скриншот интерфейса Kibana, на котором видны логи Nginx, которые были отправлены через Filebeat.
![скрин](https://github.com/dmitriypronin48/fork-cicd/blob/main/img/z4-1.jpg)




