# Домашнее задание к занятию 2 «Кластеризация и балансировка нагрузки» - `Пронин Дмитрий Андреевич`

---

### Задание 1

```
Задание 1
Составьте команду rsync, которая позволяет создавать зеркальную копию домашней директории пользователя в директорию /tmp/backup
Необходимо исключить из синхронизации все директории, начинающиеся с точки (скрытые)
Необходимо сделать так, чтобы rsync подсчитывал хэш-суммы для всех файлов, даже если их время модификации и размер идентичны в источнике и приемнике.
На проверку направить скриншот с командой и результатом ее выполнения
```
![скрин](https://github.com/dmitriypronin48/fork-cicd/blob/main/img/z1-2.jpg)




---

### Задание 2

```
Задание 2
Написать скрипт и настроить задачу на регулярное резервное копирование домашней директории пользователя с помощью rsync и cron.
Резервная копия должна быть полностью зеркальной
Резервная копия должна создаваться раз в день, в системном логе должна появляться запись об успешном или неуспешном выполнении операции
Резервная копия размещается локально, в директории /tmp/backup
На проверку направить файл crontab и скриншот с результатом работы утилиты.
```

![скрин](https://github.com/dmitriypronin48/fork-cicd/blob/main/img/z2-1.jpg)


