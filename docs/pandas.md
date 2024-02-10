# Основы Pandas

## Содержание

- [Импортирование библиотеки Pandas](#импортирование-библиотеки-pandas)
- [Создание данных](#создание-данных-вручную)
  - [Создание DataFrame через словарь](#создание-dataframe-через-словарь)
- [Загрузка данных](#загрузка-данных)
  - [Загрузка данных из Google Drive](#импорт-данных-с-google-drive)
  - [Загрузка данных из локального csv-файла](#загрузка-данных-из-локального-csv-файла)

### Импортирование библиотеки Pandas

```python
import pandas as pd
```

### Создание данных вручную

#### Создание DataFrame через словарь

```python
# Создание DataFrame из нескольких столбцов через словарь
dates = ['2021-12-31', '2022-12-31', '2023-12-31']

dict_close_prices = {'APL.Close': [100, 110, 105], 
                     'ABS.Close': [15, 16, 20]}

df = pd.DataFrame(dict_close_prices, index=dates)
```

### Загрузка данных

#### Импорт данных с Google Drive

```python
# Получение ссылки с данными
url_data = 'https://drive.google.com/file/d/1VaXAnuxVBBN604Kk50MOijHiIpMdfD3a/view?usp=sharing'
url_data = 'https://drive.google.com/uc?id=' + url_data.split('/')[-2]

# Чтение csv-файла
df = pd.read_csv(url_data, index_col=0)
```

#### Загрузка локального csv-файла

```python
df = pd.read_csv('data/example-1.csv')
```
