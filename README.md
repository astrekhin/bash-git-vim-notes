# Краткий справочник по Git

1. Установка терминала
  - [iTerm2](https://iterm2.com/) для macOS
  - [Tilix](https://gnunn1.github.io/tilix-web/) для Linux
  - [WSL](https://docs.microsoft.com/ru-ru/windows/wsl/install) для Windows
  - [Git Bash](https://git-scm.com/downloads) для всех систем
  - [Hyper.js](https://hyper.is/)
2. Запустить терминал и выполнить следующие команды:
```bash
$ git config --global user.name "Ivan Ivanov"             # Задать имя автора изменений
$ git config --global user.email my_email@gmail.com       # Задать адрес почты автора изменений
$ git config --global init.default branch main            # Задать основную ветку как 'main'
$ git config --global color.ui true                       # Включить дополнительные цвета в терминале


$ git config --list                                       # Узнать текущие настройки
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
