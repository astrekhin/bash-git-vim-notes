# LaTeX в GitHub

## Содержание

1. [Запись уравнения](#запись-уравнения)
2. [Математические операторы](#математические-операторы)
3. [Символы](#символы)
4. [Греческий алфавит](#греческий-алфавит)
5. [Пробелы](#пробелы)
6. [Примеры](#примеры)
7. [Дополнительные источники](#ссылки)

### Запись уравнения

Уравнение в строчку: $c = a + b$ (1)

```latex
Уравнение в строчку: $c = a + b$
```

Уравнение по центру с автоматическим номером:
$$
\begin{equation}
x_{1,2} = {-b \pm \sqrt{b^2 - 4ac} \over 2a}
\end{equation}
$$

```latex
Уравнение по центру: 
$$\begin{equation}
x_{1,2} = {-b \pm \sqrt{b^2 - 4ac} \over 2a}
\end{equation}$$
```

### Математические операторы

- $x + y$
- $x - y$
- $x \times y$
- $x \div y$
- $\dfrac{x}{y}$
- $\sqrt{x}$
- $x^2$

```latex
- $x + y$
- $x - y$
- $x \times y$ 
- $x \div y$
- $\dfrac{x}{y}$
- $\sqrt{x}$
- $x^2$
```

### Символы

- $=$ `=`
- $\neq$ `\neq`
- $\infty$ `\infty`
- $\sim$ `\sim`
- $\approx$ `\approx`
- $\pm$ `\pm`
- $<$ `<`
- $>$ `>`
- $\leq$ `\leq`
- $\geq$ `\geq`
- $\\#$ `\\#`
- $\\$$ `\\$`
- $\\%$ `\\%`
- $\\&$ `\\&`
- $\\_$ `\\_`
- $\left( \right)$ `$\left( \right)$`
- $\sqrt{x}$ `$\sqrt{x}$`
- $\sqrt[y]{x}$ `$\sqrt[y]{x}$`

### Греческий алфавит

- $\alpha$ `\alpha`
- $\beta$ `\beta`
- $\gamma$ `\gamma`
- $\delta$ `\delta`
- $\epsilon$ `\epsilon` или $\varepsilon$ `\varepsilon`
- $\upsilon$ `\upsilon`

### Пробелы

- Пробел, равный ширине символа **`M`** текущего шрифта $(x \quad x)$: `\quad`
- Широкий пробел, двойная ширина $(x \qquad x)$: `\qquad`
- Пробел, равный ширине обычного пробела текущего шрифта $(x \ x)$: `\`
- Минимальный пробел, равный 3/18 ширины $(x \\, x)$: `\\,`
- Средний пробел, равный 4/18 ширины $(x \\: x)$: `\\:`
- Большой пробел, равный 5/18 ширины $(x \\; x)$: `\\;`
- Отрицательный пробел, равный -3/18 ширины (наложение) $(x \\! x)$: `\\!`

### Примеры

Выделение цветом: $$\color{blue}{y=x^2}$$

```latex
\color{blue}{y=x^2}
```

$$\sqrt[3]{64}=4$$

```latex
$$\sqrt[3]{y}$$
```

$$\int_a^b y \\: \mathrm{d}x$$

```latex
$$\int_a^b y \\: \mathrm{d}x$$
```

$$\log_a b = 1$$

```latex
$$\log_a b = 1$$
```

$$\mathrm{e} = \sum_{n=0}^{\infty} \dfrac{1}{n!}$$

```latex
$$\mathrm{e} = \sum_{n=0}^{\infty} \dfrac{1}{n!}$$
```

$$\lim_{x \to 0^+} \dfrac{1}{x} = \infty$$

```latex
$$\lim_{x \to 0^+} \dfrac{1}{x} = \infty$$
```

**The Cauchy-Schwarz Inequality**
$$\left( \sum_{k=1}^n a_k b_k \right)^2 \leq \left( \sum_{k=1}^n a_k^2 \right) \left( \sum_{k=1}^n b_k^2 \right)$$

$
\sum_{\substack{
   0<i<m \\
   0<j<n
  }} 
 P(i,j)
$

**Matrix**
$$\begin{matrix}
  a & b & c \\
  d & e & f \\
  g & h & i
 \end{matrix}$$

**Формула с текстом**
$$
\begin{equation}
50 \text{ apples} \times 100 \text{ apples} 
 = \text{lots of apples}^2
\end{equation}
$$

**Matrix** 
$$
\begin{equation}
\begin{bmatrix}X\\Y\end{bmatrix}
\end{equation}
$$

**Перенос формулы с выравниванием**
$$
\begin{equation}
\begin{split}
A & = \frac{\pi r^2}{2} \\
& = \frac{1}{2} \pi r^2
\end{split}
\end{equation}
$$

**Выравнивание по вертикали**
$$
\begin{equation}
\begin{align*}
x&=y           &  w &=z              &  a&=b+c\\
2x&=-y         &  3w&=\frac{1}{2}z   &  a&=b\\
-4 + 5x&=2+y   &  w+2&=-1+w          &  ab&=cb
\end{align*}
\end{equation}
$$

**Группировка и выравнивание по центру**
$$
\begin{equation}
\begin{gather*} 
2x - 5y =  8 \\ 
3x^2 + 9y =  3a + c
\end{gather*}
\end{equation}
$$

## Ссылки

1. [Markdown and LaTeX](https://ashki23.github.io/markdown-latex.html)