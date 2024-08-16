# Домашнее задание к занятию "`Что такое DevOps. CI/CD`" - `Пронин Дмитрий Андреевич`

---

### Задание 1

###### Установка jenkins
![Установка jenkins](https://github.com/dmitriypronin48/fork-cicd/blob/main/img/z1-1.jpg)

![Установка jenkins](https://github.com/dmitriypronin48/fork-cicd/blob/main/img/z1-2.jpg)

###### Работа с Nexus и jenkins Freestyle Project
![Установка jenkins](https://github.com/dmitriypronin48/fork-cicd/blob/main/img/z1-5.jpg)
![Установка jenkins](https://github.com/dmitriypronin48/fork-cicd/blob/main/img/z1-4.jpg)
![Установка jenkins](https://github.com/dmitriypronin48/fork-cicd/blob/main/img/z1-3.jpg)

---

### Задание 2

###### Работа с pipeline declarative 
![Установка jenkins](https://github.com/dmitriypronin48/fork-cicd/blob/main/img/z2-3.jpg)
![Установка jenkins](https://github.com/dmitriypronin48/fork-cicd/blob/main/img/z2-2.jpg)
![Установка jenkins](https://github.com/dmitriypronin48/fork-cicd/blob/main/img/z2-1.jpg)

---

### Задание 3

###### Установка Nexus
* Запуск Nexus в compose
![Установка jenkins](https://github.com/dmitriypronin48/fork-cicd/blob/main/img/z3-1.jpg)
* Создание raw репозитория
![Установка jenkins](https://github.com/dmitriypronin48/fork-cicd/blob/main/img/z3-2.jpg)

* Создание pipeline
```
pipeline {
 agent any
 stages {
  stage('Git') {
   steps {git 'https://github.com/netology-code/sdvps-materials.git'}
  }
  stage('Test') {
   steps {
    sh '/usr/local/go/bin/go test .'
   }
  }
  stage('Build') {
   steps {
    sh '/usr/local/go/bin/go build -a -installsuffix nocgo -o go_result_$BUILD_NUMBER .'
   }
  }
  stage('Push') {
   steps {
    sh 'curl -v --user "admin:admin" --upload-file ./go_result_$BUILD_NUMBER http://localhost:8081/repository/raw_repo/go_result_$BUILD_NUMBER'   }
  }
 }
}
```
---


