# Репозиторий создан для внутренного пользования, представляет собой краткие заметки о git без какой-либо структуры.

## Краткая информация по Git

1. Установка терминала
  - [iTerm2](https://iterm2.com/) для macOS
  - [Tilix](https://gnunn1.github.io/tilix-web/) для Linux
  - [WSL](https://docs.microsoft.com/ru-ru/windows/wsl/install) Linux для Windows
  - [Git Bash](https://git-scm.com/downloads) - установлено!
  - [Hyper.js](https://hyper.is/)
2. Запустить терминал и выполнить следующие команды:
```bash
$ git config --list                                       # Узнать текущие настройки

$ git config --global user.name "Ivan Ivanov"             # Задать имя автора изменений
$ git config --global user.email my_email@gmail.com       # Задать адрес почты автора изменений
$ git config --global init.default branch main            # Задать основную ветку как 'main', если по-умолчанию стоит 'master'
$ git config --global color.ui true                       # Включить дополнительные цвета в терминале, если они отключены
```

3. Создать папку с проектом и перейти в нее
```bash
$ cd C:
$ mkdir my-project
$ cd my-project
```
4. Сделать инициализацию папки с проектом
```bash
$ git init                                                # Создание нового проекта из директории проекта (создается поддиректория .git)
```
5. Добавление удаленного репозитория
```bash
## my_name - имя пользователя
## my_project - название репозитория
$ git remote add origin http://github.com/my_name/my_project.git 
```
6. Установка отслеживания локальной ветки и ветки удаленного репозитория
```bash
$ git push -u origin main
# Аналогичная команда
$ git push --set-upstream origin main
```
#### Другие команды:
```bash
$ git clone https://github.com/libgit2/libgit2            # Клонирование репозитория с сайта в директорию 'libgit2'
$ git clone https://github.com/libgit2/libgit2 my_dir     # Клонирование репозитория с сайта в директорию 'my_dir'
```

#### Основные команды
```bash
$ touch test.py                        # Создать файл с именем 'test.py'
$ git status                           # Проверка текущего статуса репозитория
$ git add hello.py                     # Добавить файл для слежения
$ git add .                            # Добавить все файлы
$ git commit -m "Update"               # Сохранить изменения с коротким пояснением
$ git diff                             # Показывает различия предыдущей и текущей версией файла
```

[Основы командной строки](https://github.com/astrekhin/git-tutorial/blob/main/git.md)
