[Index](https://github.com/astrekhin/py-tutorials)

# Краткая информация по Git

1. Установка терминала
  - [iTerm2](https://iterm2.com/) для macOS
  - [Tilix](https://gnunn1.github.io/tilix-web/) для Linux
  - [WSL](https://docs.microsoft.com/ru-ru/windows/wsl/install) Linux для Windows
  - [Git Bash](https://git-scm.com/downloads) - установлено!
  - [Hyper.js](https://hyper.is/)

2. Определение параметров по-умолчанию
```bash
# В терминале ввести следующие команды:
$ git config --list                                       # Узнать текущие настройки git

$ git config --global user.name "Ivan Ivanov"             # Задать имя автора изменений на все проекты (глобально)
$ git config --global user.email my_email@gmail.com       # Задать адрес почты автора изменений на все проекты (глобально)
$ git config --global init.default branch main            # Задать основную ветку как 'main', если по-умолчанию стоит 'master'
$ git config --global color.ui true                       # Включить дополнительные цвета в терминале, если они отключены
```

3. Создание репозитория

  - Вариант 1. Создание пустого локального репозитория <br>
    - Создание директории с именем проекта
    ```bash
    $ cd C:
    $ mkdir my-project
    $ cd my-project
    # Создание пустого репозитория из директории проекта (создается поддиректория .git)
    $ git init
    ```
    - Добавление удаленного репозитория
    ```bash
    # origin - название ветки по-умолчанию
    # my_name - имя пользователя
    # my_project - название репозитория
    $ git remote add origin http://github.com/my_name/my_project.git 
    ```
    - Установка отслеживания локальной ветки и ветки удаленного репозитория
    ```bash
    $ git push -u origin main
    # Аналогичная команда
    $ git push --set-upstream origin main
    ```

  - Вариант 2. Клонирование (скачивание) удаленного репозитория на локальную машину
    ```bash
    # Клонирование удаленного репозитория в директорию 'libgit2'
    $ git clone https://github.com/libgit2/libgit2                # Имя локального репозитория соответствует имени удаленного репозитория
    # Клонирование удаленного репозитория в директорию 'my_dir'
    $ git clone https://github.com/libgit2/libgit2 my_dir         # Имя локального репозитория задается пользователес 
    ```

4. Основные команды сработы с локальным репозиторием 
```bash
# Создание нового файла в локальном репозитории
# touch <file name>
$ touch hello.py

# Проверка состояния локального репозитория
$ git status

# Добавление файла в локальный репозиторий
# git add <file name>
$ git add hello.py

# Фиксация измений локального репозитория
# -m "Комментарий к коммиту" (-m от слова message)
$ git commit -m "Add hello.py"

# Загрузка локального репозитория на удаленный сервер
$ git push

# Скачивание удаленного репозитория на локальнцю машину
$ git pull

# Просмотр различий предыдущей и текущей версией файла
$ git diff  

# Скачивание изменений с удаленного репозитория на локальный
$ git fetch

# Объединение изменений
$ git merge 

# Скачивание и объединение изменений удаленного репозитория с локальным
# Аналог выполнения команд fetch and merge
$ git pull
```



