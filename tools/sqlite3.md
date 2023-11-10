# SQLite3

## Содержание

- [Установка SQLite3 на Colab](#установка-sqlite3-на-colab)
  - [Обновление SQLite3 в Colab](#обновление-sqlite3-в-colab)
  - [Подключение SQLite3](#подключение-sqlite3-и-проверка-установленной-версии)
- [Создание базы данных SQLite3 в Google Drive](#создание-базы-данных-sqlite3-в-google-drive)
- [Создание таблицы](#создание-таблицы)
  - [Добавление данных в таблицу](#добавление-данных-в-таблицу)


### Установка SQLite3 на Colab

По умолчанию в Colab стоит непоследняя версия SQLite3 (3.22.0). Если требуется использовать последнюю версию SQlite3, то ее необходимо обновить.

#### Обновление SQLite3 в Colab

```bash
!curl https://www.sqlite.org/src/tarball/sqlite.tar.gz?r=release | tar xz
%cd sqlite/
!./configure
!make sqlite3.c
%cd /content
!npx degit coleifer/pysqlite3 -f
!cp sqlite/sqlite3.[ch] .
!python setup.py build_static build
!cp build/lib.linux-x86_64-3.7/pysqlite3/_sqlite3.cpython-37m-x86_64-linux-gnu.so \
     /usr/lib/python3.7/lib-dynload/
```

После завершения обновления SQLite3 необходимо перезапустить среду выполнения через MENU: Runtime > Restart runtime (`Ctrl + M + .` on Windows).

#### Подключение SQLite3 и проверка установленной версии

```python
import sqlite3

sqlite3.sqlite_version  # 3.39.3 
```

### Создание базы данных SQLite3 в Google Drive

Для монтирования образа Google Drive в Colab необходимо пройти аутентификацию.

```python
# Получение ссылки для аутентификации
from google.colab import drive

drive.mount('/content/drive')
```

По окончании монтирования получаем сообщение `“Mounted at /content/drive”`. Теперь можно взаимодействовать с Google Drive.

`path` - путь к базе данных. Если по данному пути нет БД, то она создается.

```python
path = '.drive/My Drive/my-db/test.db'

conn = sqlite3.connect(path)
print("Opened database successfully");
```

### Создание таблицы

Создание таблицы `employers_data` с колонками `first_name`, `last_name`, `age` и `wage`.

```python
conn.execute('''
CREATE TABLE IF NOT EXISTS employers_data(first_name text, 
                      last_name text, 
                      age integer, 
                      wage integer);''')

conn.commit()

print("Table created successfully");

conn.commit()
```

#### Добавление данных в таблицу с помощью SQL-запроса

```python
# INSERTING VALUES

conn.execute("INSERT INTO employers_data VALUES('Ivan', 'Petrov', 20, 10000);")
conn.execute("INSERT INTO employers_data VALUES('Vera', 'Sokolova', 19, 10000);")
conn.execute("INSERT INTO employers_data VALUES('Oleg', 'Ivanov', 30, 50000);")
conn.execute("INSERT INTO employers_data VALUES('Alex', 'Genov', 45, 75000);")
conn.execute("INSERT INTO employers_data VALUES('Maria', 'Titova', 16, 7500);")
conn.execute("INSERT INTO employers_data VALUES('Petr', 'Nemov', 35, 35000);")

conn.commit()
```

#### Добавление данных в таблицу с помощью Pandas

Источник: [Pandas Docs](https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.DataFrame.to_sql.html)

```python

```