# Load CSV files into Colab

```python
# Подключение библиотеки pandas
import pandas as pd
```

## 1. From Github (Files < 25MB)

```python
# Подключение библиотеки pandas
import pandas as pd

# Сохранение данных из GitHub в Data Frame
# url = 'raw_GH_link'
url = 'https://raw.githubusercontent.com/astrekhin/tools-notes/main/tools/db/example-1.csv'
df1 = pd.read_csv(url)
df1
```

## 2. From a local drive

```python
# Загрузка файла с компьютера
from google.colab import files
uploaded = files.upload()
```

```python
# Подключение библиотеки pandas
import pandas as pd

# Сохранение данных загруженного файла в DataFrame
df2 = pd.read_csv('example-2.csv')
```

Отключение среды выполнения происходит в случае 90 минутного простоя или 12-ти часового использования, после чего все данные удаляются. Поэтому все данные необходимо сохранять.

```python
# Сохранение данных на локальный компьютер
from google.colab import files
files.download('/content/example-2.cvs')
```

## 3. From Google Drive

```python
from google.colab import drive
drive.mount("/drive")
```

```python
# Подключение библиотеки pandas
import pandas as pd

# Загрузка данных из cvs в DataFrame
df3 = pd.read_csv('/drive/My Drive/my-db/Example_1.csv')
```
