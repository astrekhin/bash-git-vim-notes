# PostgreSQL

## Установка и запуск сервера PostgreSQL на Colab

```bash
# Install postgresql server
!sudo apt-get -y -qq update
!sudo apt-get -y -qq install postgresql
!sudo service postgresql start

# Setup a password `postgres` for username `postgres`
!sudo -u postgres psql -U postgres -c "ALTER USER postgres PASSWORD 'postgres';"
```

## Создание движка

Для создания движка (объекта `Engine`) используется функция `create_engine()` из пакета `sqlalchemy`. В базовом виде она принимает только строку подключения. Последняя включает информацию об источнике данных. Обычно это приблизительно следующий формат:

```dialect+driver://username:password@host:port/database```

- `dialect` — это имя базы данных (mysql, postgresql, mssql, oracle и так далее).
- `driver` — используемый DBAPI. Этот параметр является необязательным. Если его не указать будет использоваться драйвер по умолчанию (если он установлен).
- `username` и `password` — данные для получения доступа к базе данных.
- `host` — расположение сервера базы данных.
- `port` — порт для подключения.
- `database` — название базы данных.

```python
# Create engine
from sqlalchemy import create_engine

con = create_engine('postgresql+psycopg2://postgres:postgres:@localhost:5432/postgres')
```

## Дополнительные настройки

```python
# Подключение библиотек для работы с данными
import pandas as pd
import numpy as np
```

```python
# Создание обертки для удобного чтения SQL
def select(sql):
    return pd.read_sql(sql, con)
```

Если файл с данными большой и чтение `sql` происходит медленно, то можно увеличить скорость чтения, используя [Insertion method](https://pandas.pydata.org/pandas-docs/stable/user_guide/io.html#insertion-method).

```python
# Alternative to_sql() *method* for DBs that support COPY FROM
import csv
from io import StringIO

def psql_insert_copy(table, conn, keys, data_iter):
    """
    Execute SQL statement inserting data

    Parameters
    ----------
    table : pandas.io.sql.SQLTable
    conn : sqlalchemy.engine.Engine or sqlalchemy.engine.Connection
    keys : list of str
        Column names
    data_iter : Iterable that iterates the values to be inserted
    """
    # gets a DBAPI connection that can provide a cursor
    dbapi_conn = conn.connection
    with dbapi_conn.cursor() as cur:
        s_buf = StringIO()
        writer = csv.writer(s_buf)
        writer.writerows(data_iter)
        s_buf.seek(0)

        columns = ', '.join(['"{}"'.format(k) for k in keys])
        if table.schema:
            table_name = '{}.{}'.format(table.schema, table.name)
        else:
            table_name = table.name

        sql = 'COPY {} ({}) FROM STDIN WITH CSV'.format(
            table_name, columns)
        cur.copy_expert(sql=sql, file=s_buf)
```
