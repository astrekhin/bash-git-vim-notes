# Краткий справочник по Git

1. Установка терминала ([Git Bash](https://git-scm.com/downloads), [Hyper.js](https://hyper.is/) и др.)
2. Запустить терминал и выполнить следующие команды:
```bash
$ git config --global user.name "Ivan Ivanov"
$ git config --global user.email my_email@gmail.com
$ git config --global init.default branch main
```
3. Создать папку с проектом и перейти в нее
```bash
$ cd C:
$ mkdir my-project
$ cd my-project
```
4. Сделать инициализацию папки с проектом
```bash
$ git init
```



#### Основные команды
```bash
$ git status                           # Проверка текущего статуса репозитория
$ git add hello.py                     # Добавить файл для слежения
$ git add .                            # Добавить все файлы
$ git commit -m "Update"               # Сохранить изменения с коротким пояснением
```
