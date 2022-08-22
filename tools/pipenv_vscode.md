# Найстрйка VSCode, Jupyter, and pipenv

## *Содержание*

1. [Создание проекта](#создание-директории-и-виртуального-окружения-проекта)
2. [Создание файла](#создание-файла-для-теста-виртуального-окружения)

### *Создание директории и виртуального окружения проекта*

Для создания проекта заходим в терминал и выполняем следущие команды:

```bash
# Создание директории тестового проекта
mkdir my-test-project
cd my-test-project

# Создание виртуального окружения проекта в версии Python 3
pipenv --three
```

В директории проекта создастся файл `Pipfile`

```bash
$ pwd
/c/my-test-project

$ ls
Pipfile
```

В директории пользователя создастся виртуальное окружение

```bash
$ pipenv --venv
C:\Users\%username%\.virtualenvs\my-test-project-_Wk2lJ3s  # Windows 10
```

### *Создание файла для теста виртуального окружения*

Для примера создадим простенький файл c названием `npf-test`, суть которого будет в решении следующей задачи:

What is the future value after 10 years of saving $100 now, with an additional monthly savings of $100. Assume the interest rate is 5% (annually) compounded monthly?

```python
# fv(rate, nper, pmt, pv[, when]) - compute future value
import numpy_financial as npf

rate = .05/12  # monthly
nper = 10*12   # months
pmt = 100
pv = 100

fv = npf.fv(rate, nper, -pmt, -pv)

print("Task:")
print("What is the future value after 10 years of saving $100 now, with an additional monthly savings of $100. Assume the interest rate is 5% (annually) compounded monthly?")
print("Solution:")
print(f"future value = {fv:.2f}")
```

Выполним данный файл интерпретатором Python

```bash
# Локация интерпретатора Python
$ pipenv --py
C:\Users\%username%\.virtualenvs\my-test-project-_Wk2lJ3s\Scripts\python.exe  # Windows 10

$ python npf-test.py
```

Если глобально модуль `numpy_financial` не установлен, то результат выполнения программы выдаст ошибку `ModuleNotFoundError: No module named 'numpy_financial'`

```bash
# Установка необходимых модулей (пример)
pipenv install numpy_funancial
```

### *Настройка VSCode*

`Ctrl + Shift + P` необходимо выбрать ввести `Python:`

```json
"python.venvPath": "C:\\Users\\%%USERNAME%%\\.virtualenvs"
```
