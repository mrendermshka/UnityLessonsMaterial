
# Порожній Python файл і його еквівалент у C#

## Порожній файл у Python

Порожній файл Python виглядає так:

```python
````

У ньому немає коду.
Коли Python запускає такий файл, він просто відкриває його, бачить що виконувати нічого, і завершує роботу.
Файл сам по собі є точкою входу. Якщо в ньому є код, він виконується зверху вниз. Якщо коду немає, нічого не відбувається.

---

## Мінімальний еквівалент у C# (.NET Framework Console Application)

У C# неможливо запустити повністю порожній файл. Мінімальний варіант виглядає так:

```csharp
using System;

class Program
{
    static void Main()
    {
    }
}
```

Цей код запускається і одразу завершується, не роблячи нічого. За поведінкою це відповідає порожньому Python файлу.

---

## Чому в C# є код, а в Python ні

Різниця не в мові, а в моделі виконання.

У Python файл є виконуваним скриптом. Інтерпретатор читає файл і одразу виконує всі інструкції, які бачить. Якщо інструкцій немає, виконання просто завершується.

У C# файл не є скриптом. Він описує структуру програми. CLR не може здогадатися, з якого місця почати виконання, тому вимагає явну точку входу. Цією точкою входу завжди є метод `Main`.

Навіть якщо програма нічого не робить, `Main` повинен існувати, інакше компіляція неможлива.

---

## Що таке `using` і навіщо він потрібен

Рядок:

```csharp
using System;
```

не означає виконання коду. Він не завантажує бібліотеки під час запуску і не має побічних ефектів.

`using` повідомляє компілятору, що імена типів з простору імен `System` можна використовувати без повного імені.

Без `using` довелося б писати так:

```csharp
System.Console.WriteLine("Hello");
```

З `using` достатньо:

```csharp
Console.WriteLine("Hello");
```

---

## Порівняння `using` у C# та `import` у Python

У Python:

```python
import os
```

це виконувана дія. Модуль завантажується, і весь код на верхньому рівні в ньому виконується. Можуть створюватися обʼєкти, змінюватися глобальний стан, запускатися логіка.

У C#:

```csharp
using System;
```

це лише інструкція для компілятора.
Вона не виконується під час запуску програми і не має жодного runtime-ефекту.

Тому правильно думати про `using` як про синтаксичний аналог `import`, але не як про функціональний аналог. За сенсом це скоріше скорочення імен, ніж завантаження модуля.

---

# Приклад 1. Виведення тексту в консоль

```csharp
// Python: print("Hello, world!")
using System;

// Python: def main():
class Program
{
    // Python: код файлу виконується одразу, а в C# старт тут
    static void Main()
    {
        // Python: print("Hello, world!")
        Console.WriteLine("Hello, world!");
    }
}
````

Пояснення
У Python достатньо написати `print`, і рядок одразу виконується, бо файл є точкою входу.
У C# виведення можливе тільки всередині `Main`, бо саме він є стартом програми.

---

# Приклад 2. Зчитування тексту з клавіатури

```csharp
// Python: input("Enter text: ")
using System;

// Python: def main():
class Program
{
    // Python: виконання починається з першого рядка файлу
    static void Main()
    {
        // Python: print("Enter text: ")
        Console.WriteLine("Enter text:");

        // Python: text = input()
        string text = Console.ReadLine();

        // Python: print(text)
        Console.WriteLine(text);
    }
}
```

Пояснення
У Python `input()` одночасно і показує запит, і читає введений текст.
У C# ці дії розділені: `Console.WriteLine` показує повідомлення, `Console.ReadLine` читає введення з клавіатури.

---

# Ключова різниця, яку важливо запамʼятати

У Python код виконується одразу, як інтерпретатор читає файл.
У C# код лише описується, а виконуватися починає тільки те, що викликано з `Main`.

Тому навіть прості дії, які в Python займають один рядок, у C# завжди знаходяться всередині структури програми.

```csharp

# Зчитування даних з клавіатури в C# та пояснення типізації

Нижче показаний один C# Console Application, який зчитує різні типи даних з клавіатури.  
Перед КОЖНИМ рядком є коментар з тим, як це виглядало б у Python.

---

## Повний приклад коду

```csharp
// Python: (import не обовʼязковий для print/input)
using System;

// Python: файл є точкою входу
class Program
{
    // Python: виконання починається одразу з першого рядка файлу
    static void Main()
    {
        // Python: text = input("Enter text: ")
        Console.WriteLine("Enter text:");
        // Python: text = input()
        string text = Console.ReadLine();

        // Python: number = int(input("Enter integer: "))
        Console.WriteLine("Enter integer:");
        // Python: number = int(input())
        int integerNumber = int.Parse(Console.ReadLine());

        // Python: value = float(input("Enter float: "))
        Console.WriteLine("Enter float (float):");
        // Python: value = float(input())
        float floatNumber = float.Parse(Console.ReadLine());

        // Python: value = float(input("Enter double: "))
        Console.WriteLine("Enter double:");
        // Python: value = float(input())
        double doubleNumber = double.Parse(Console.ReadLine());

        // Python: char_value = input("Enter char: ")[0]
        Console.WriteLine("Enter single character:");
        // Python: char_value = input()[0]
        char character = char.Parse(Console.ReadLine());

        // Python: print(text, integerNumber, floatNumber, doubleNumber, character)
        Console.WriteLine(text);
        Console.WriteLine(integerNumber);
        Console.WriteLine(floatNumber);
        Console.WriteLine(doubleNumber);
        Console.WriteLine(character);
    }
}
````

---

## Що тут відбувається і чому це виглядає складніше ніж у Python

У Python змінна не має типу наперед. Тип зʼявляється в момент присвоєння значення.
Один і той самий ідентифікатор може в різний момент бути рядком, числом або списком.

```python
x = 10
x = "hello"
x = 3.14
```

Python дозволяє це, бо він динамічно типізований.

У C# змінна МАЄ тип завжди.
Тип визначає:

* скільки памʼяті потрібно
* які операції дозволені
* як CLR буде з нею працювати

Тому перший раз, коли змінна зʼявляється, перед нею ОБОВʼЯЗКОВО вказується тип:

```csharp
string text;
int integerNumber;
float floatNumber;
double doubleNumber;
char character;
```

Після цього змінна вже не може змінити тип.

---

## Чому `Console.ReadLine()` завжди повертає string

Клавіатура завжди повертає текст.
Навіть якщо ти вводиш `123`, фізично це символи `1`, `2`, `3`.

Тому в C#:

```csharp
Console.ReadLine();
```

завжди має тип `string`.

Щоб отримати число, потрібне явне перетворення:

```csharp
int.Parse(...)
float.Parse(...)
double.Parse(...)
char.Parse(...)
```

У Python це приховано всередині `int()` і `float()`, але логіка та сама.

---

## Чому float і double це різні типи

У Python `float` це завжди подвійна точність.
У C# є два різні типи:

`float`
Займає менше памʼяті, менша точність, швидший.

`double`
Займає більше памʼяті, більша точність, використовується за замовчуванням.

Тому в C# ти свідомо обираєш, чим платиш: памʼяттю чи точністю.

---

## Головна ідея, яку треба запамʼятати

Python дозволяє думати “що це зараз”.
C# змушує думати “чим це є завжди”.

---

# Умовні оператори в C# та Python: різниця і сенс

Нижче показані умовні оператори `if / else / elif` у Python  
і їх повний еквівалент у C# (`if / else if / else`).

Перед КОЖНИМ рядком C# є коментар з тим, як це виглядало б у Python.

---

## Простий if

### Python

```python
x = 10

if x > 5:
    print("x is greater than 5")
````

### C#

```csharp
// Python: x = 10
int x = 10;

// Python: if x > 5:
if (x > 5)
{
    // Python: print("x is greater than 5")
    Console.WriteLine("x is greater than 5");
}
```

Пояснення
У C# умова ЗАВЖДИ береться в круглі дужки.
Тіло умови ЗАВЖДИ береться у фігурні дужки, навіть якщо рядок один.

---

## if + else

### Python

```python
x = 3

if x > 5:
    print("greater")
else:
    print("not greater")
```

### C#

```csharp
// Python: x = 3
int x = 3;

// Python: if x > 5:
if (x > 5)
{
    // Python: print("greater")
    Console.WriteLine("greater");
}
else
{
    // Python: print("not greater")
    Console.WriteLine("not greater");
}
```

Пояснення
У Python блоки визначаються відступами.
У C# блоки визначаються фігурними дужками, а відступи лише для читабельності.

---

## elif vs else if

### Python

```python
x = 0

if x > 0:
    print("positive")
elif x < 0:
    print("negative")
else:
    print("zero")
```

### C#

```csharp
// Python: x = 0
int x = 0;

// Python: if x > 0:
if (x > 0)
{
    // Python: print("positive")
    Console.WriteLine("positive");
}
// Python: elif x < 0:
else if (x < 0)
{
    // Python: print("negative")
    Console.WriteLine("negative");
}
else
{
    // Python: print("zero")
    Console.WriteLine("zero");
}
```

Пояснення
`elif` у Python це синтаксичне скорочення.
У C# це завжди `else if`, окремі ключові слова.
---


## Логічні оператори

### Python

```python
if x > 0 and x < 10:
    print("between")
```

### C#

```csharp
// Python: if x > 0 and x < 10:
if (x > 0 && x < 10)
{
    // Python: print("between")
    Console.WriteLine("between");
}
```

Відповідність операторів:

* Python `and` → C# `&&`
* Python `or` → C# `||`
* Python `not` → C# `!`

---

## Порівняння значень

### Python

```python
if a == b:
    print("equal")
```

### C#

```csharp
// Python: if a == b:
if (a == b)
{
    // Python: print("equal")
    Console.WriteLine("equal");
}
```

Важливо
У C# `=` це присвоєння, `==` це порівняння.
Те саме і в Python, але в C# компілятор суворіше це контролює.

---

## Що НЕ дозволено в C#, але дозволено в Python

### Python

```python
x = 10

if x:
    print("x is truthy")
```

### C# так НЕ МОЖНА

```csharp
int x = 10;

// ❌ помилка компіляції
if (x)
{
    Console.WriteLine("x is truthy");
}
```

### Правильно в C#

```csharp
// Python: if x:
if (x != 0)
{
    Console.WriteLine("x is non-zero");
}
```

Пояснення
У Python будь-що може бути умовою.
У C# умова ЗАВЖДИ повинна бути `bool`.

Це частина строгої типізації.

---

## Ключова різниця мислення

Python дозволяє писати умови інтуїтивно і гнучко.
C# змушує формулювати умову логічно і явно.

Python думає:
"Чи це істина в даний момент?"

C# думає:
"Чи це вираз типу bool?"

---
## ЗАВДАННЯ 1.

### Умова завдання

Напиши програму на **C# (.NET Framework Console Application)**, яка:

1) Запитує імʼя користувача  
   `Enter your name:`

2) Зчитує імʼя з клавіатури

3) Запитує вік користувача  
   `Enter your age:`

4) Зчитує вік і перетворює його в число типу `int`

5) Виводить:
   - `Hello, <name>`
   - `Your age is <age>`

6) За допомогою умов `if / else if / else` виводить:
   - якщо вік < 18 → `You are under 18`
   - якщо вік від 18 до 65 включно → `You are an adult`
   - якщо вік > 65 → `You are a senior`


# Різниця між циклами for та while у Python і C#

Нижче показано, як працюють цикли `for` та `while` у Python  
і як вони виглядають у C# (.NET Framework Console Application).

Перед КОЖНИМ рядком C# є коментар з тим, як це виглядало б у Python.

---

## while цикл

### Python

```python
i = 0

while i < 5:
    print(i)
    i += 1
````

### C#

```csharp
// Python: i = 0
int i = 0;

// Python: while i < 5:
while (i < 5)
{
    // Python: print(i)
    Console.WriteLine(i);

    // Python: i += 1
    i++;
}
```

Пояснення
Логіка однакова в обох мовах.
У C#:

* умова завжди в круглих дужках
* тіло циклу завжди у фігурних дужках
* умова повинна бути типу `bool`

---

## for цикл як лічильник

### Python

```python
for i in range(0, 5):
    print(i)
```

### C#

```csharp
// Python: for i in range(0, 5):
for (int i = 0; i < 5; i++)
{
    // Python: print(i)
    Console.WriteLine(i);
}
```

Пояснення
Це КЛЮЧОВА різниця мислення.

Python `for` це:

* ітерація по послідовності

C# `for` це:

* класичний цикл з лічильником

У C# цикл `for` складається з трьох частин:

* ініціалізація змінної
* умова
* крок

У Python `range()` створює послідовність чисел, по якій іде цикл.

---

## for як ітерація по колекції

### Python

```python
items = ["a", "b", "c"]

for item in items:
    print(item)
```

### C#

```csharp
// Python: items = ["a", "b", "c"]
string[] items = { "a", "b", "c" };

// Python: for item in items:
foreach (string item in items)
{
    // Python: print(item)
    Console.WriteLine(item);
}
```

Пояснення
У C# для цього використовується `foreach`, а не `for`.

Причина
C# чітко розділяє:

* цикл по індексу
* цикл по елементах

Python поєднує це в одному `for`.

---

## break і continue

### Python

```python
for i in range(10):
    if i == 5:
        break
    if i == 2:
        continue
    print(i)
```

### C#

```csharp
// Python: for i in range(10):
for (int i = 0; i < 10; i++)
{
    // Python: if i == 5:
    if (i == 5)
    {
        // Python: break
        break;
    }

    // Python: if i == 2:
    if (i == 2)
    {
        // Python: continue
        continue;
    }

    // Python: print(i)
    Console.WriteLine(i);
}
```

Пояснення
`break` і `continue` працюють однаково в обох мовах.
Різниця тільки в синтаксисі.

---

## while True vs нескінченний цикл

### Python

```python
while True:
    print("loop")
```

### C#

```csharp
// Python: while True:
while (true)
{
    // Python: print("loop")
    Console.WriteLine("loop");
}
```

Пояснення
У Python `True` це булеве значення.
У C# `true` теж булеве, але завжди з малої літери.

---

## Що НЕ можна в C#, але можна в Python

### Python

```python
while x:
    print("x is true")
```

### C# так НЕ МОЖНА

```csharp
int x = 5;

// ❌ помилка компіляції
while (x)
{
    Console.WriteLine("x is true");
}
```

### Правильно в C#

```csharp
// Python: while x:
while (x != 0)
{
    Console.WriteLine("x is non-zero");
    x--;
}
```

Пояснення
У Python будь-який обʼєкт може бути умовою.
У C# умова циклу ЗАВЖДИ повинна бути `bool`.

---

## Головна концептуальна різниця

Python:

* `for` означає "йти по чомусь"
* `while` означає "поки істина"

C#:

* `for` означає "рахувати"
* `foreach` означає "йти по колекції"
* `while` означає "поки умова bool"

Python приховує механіку.
C# змушує її явно описувати.
---
# Завдання 2. Цикли (for та while) у C#

## Мета  
Закріпити:
- використання циклів `for` та `while`
- роботу з лічильниками
- умовні перевірки всередині циклів
- базове мислення ітераціями

---

## Умова завдання

Напиши програму на **C# (.NET Framework Console Application)**, яка:

1) Запитує у користувача ціле число `N`

2) За допомогою циклу `for`:
   - виводить усі числа від `1` до `N` включно
   - кожне число виводиться з нового рядка

3) За допомогою циклу `while`:
   - виводить усі парні числа від `0` до `N` включно
   - якщо `N` відʼємне, цикл не повинен виконуватися

# Функції у Python та C#: різниця підходів і мислення

Нижче показано, як виглядають функції у Python  
і як ті самі ідеї реалізуються у C# (.NET Framework Console Application).

Перед КОЖНИМ рядком C# є коментар з прикладом, як це виглядало б у Python.

---

## Найпростіша функція без параметрів

### Python

```python
def say_hello():
    print("Hello")

say_hello()
````

### C#

```csharp
// Python: def say_hello():
static void SayHello()
{
    // Python: print("Hello")
    Console.WriteLine("Hello");
}

// Python: say_hello()
SayHello();
```

Пояснення
У Python функцію можна оголосити будь-де, і код одразу доступний.
У C# функція завжди належить класу і викликається тільки з місця виконання, зазвичай з `Main`.

---

## Функція з параметрами

### Python

```python
def greet(name):
    print("Hello", name)

greet("Alex")
```

### C#

```csharp
// Python: def greet(name):
static void Greet(string name)
{
    // Python: print("Hello", name)
    Console.WriteLine("Hello " + name);
}

// Python: greet("Alex")
Greet("Alex");
```

Пояснення
У Python параметр не має типу наперед.
У C# тип параметра ОБОВʼЯЗКОВИЙ.

---

## Функція з поверненням значення

### Python

```python
def add(a, b):
    return a + b

result = add(2, 3)
```

### C#

```csharp
// Python: def add(a, b):
static int Add(int a, int b)
{
    // Python: return a + b
    return a + b;
}

// Python: result = add(2, 3)
int result = Add(2, 3);
```

Пояснення
У C# тип значення, яке повертається, пишеться ПЕРЕД назвою функції.
`void` означає що функція нічого не повертає.

---

## Чому в C# потрібно вказувати тип повернення

У Python тип визначається під час виконання:

```python
def f():
    return 10
```

У C# компілятор повинен знати тип ще ДО запуску програми.
Це дозволяє:

* перевірити помилки
* оптимізувати код
* гарантувати коректність

Тому C# не дозволяє "повернути що завгодно".

---

## Кілька параметрів різних типів

### Python

```python
def format_user(name, age):
    return name + " " + str(age)
```

### C#

```csharp
// Python: def format_user(name, age):
static string FormatUser(string name, int age)
{
    // Python: return name + " " + str(age)
    return name + " " + age.ToString();
}
```

Пояснення
У Python `str()` це універсальне перетворення.
У C# кожен тип має власні методи або явні перетворення.

---

## Функція без return

### Python

```python
def log(message):
    print(message)
```

### C#

```csharp
// Python: def log(message):
static void Log(string message)
{
    // Python: print(message)
    Console.WriteLine(message);
}
```

Пояснення
У Python така функція повертає `None`.
У C# така функція має тип `void`.

---

Пояснення
У C# доступ до змінних залежить від:

* `static` або instance
* класу


---

## Ключова різниця мислення

Python:

* функція це просто обʼєкт
* типи не обовʼязкові
* виконання гнучке

C#:

* функція це метод класу
* типи обовʼязкові
* виконання строго контрольоване

Python дозволяє швидко писати.
C# змушує думати наперед.

---

## Головне, що треба запамʼятати

Типи параметрів і повернення в C# не для ускладнення.
Вони існують, щоб компʼютер і розробник точно знали, що відбувається.

## Завдання 3. Функція

### Мета  
Закріпити:
- оголошення функцій
- параметри
- повернення значення
- роботу з типами

### Умова

Напиши програму, яка:

1) Зчитує з клавіатури два цілих числа  
2) Викликає окрему функцію, яка:
   - приймає ці два числа як параметри
   - повертає їх суму
3) Виводить результат у консоль у вигляді:  
   `Sum is: <result>`

### Вимоги

- Функція повинна бути окремим методом
- Типи параметрів і тип повернення повинні бути вказані явно
- Функція не повинна зчитувати дані з клавіатури
- Весь код виклику знаходиться в `Main`

### Підказка мислення

У Python це був би `def add(a, b): return a + b`  
У C# потрібно явно вказати типи і місце виклику.


---
# Класи у Python та C#: різниця підходів і мислення

Класи це фінальний і найважливіший елемент різниці між Python і C#.  
Тут різниця не лише в синтаксисі, а в самій філософії мов.

Нижче всі приклади показані так:
- спочатку ідея на Python
- потім C# код
- перед КОЖНИМ рядком C# є коментар з Python-аналогом

---

## Найпростіший клас без логіки

### Python

```python
class User:
    pass

u = User()
````

### C#

```csharp
// Python: class User:
class User
{
}

// Python: u = User()
User u = new User();
```

Пояснення
У Python клас може бути порожнім.
У C# клас теж може бути порожнім, але створення обʼєкта ЗАВЖДИ через `new`.

---

## Поля класу (змінні всередині класу)

### Python

```python
class User:
    def __init__(self, name):
        self.name = name

u = User("Alex")
print(u.name)
```

### C#

```csharp
// Python: class User:
class User
{
    // Python: self.name = name
    public string Name;

    // Python: def __init__(self, name):
    public User(string name)
    {
        // Python: self.name = name
        Name = name;
    }
}

// Python: u = User("Alex")
User u = new User("Alex");

// Python: print(u.name)
Console.WriteLine(u.Name);
```

Пояснення
У Python поля можуть зʼявлятися динамічно.
У C# всі поля мають бути оголошені заздалегідь з типом.

---

## Методи класу

### Python

```python
class User:
    def say_hello(self):
        print("Hello")

u = User()
u.say_hello()
```

### C#

```csharp
// Python: class User:
class User
{
    // Python: def say_hello(self):
    public void SayHello()
    {
        // Python: print("Hello")
        Console.WriteLine("Hello");
    }
}

// Python: u = User()
User u = new User();

// Python: u.say_hello()
u.SayHello();
```

Пояснення
`self` у Python передається явно.
`this` у C# передається автоматично і зазвичай не пишеться.

---

## Конструктор

### Python

```python
class User:
    def __init__(self, name):
        self.name = name
```

### C#

```csharp
// Python: class User:
class User
{
    // Python: self.name
    public string Name;

    // Python: def __init__(self, name):
    public User(string name)
    {
        // Python: self.name = name
        Name = name;
    }
}
```

Пояснення
`__init__` у Python це звичайний метод.
Конструктор у C# це спеціальний метод з іменем класу.

---

## Властивості (property) проти прямого доступу

### Python

```python
class User:
    def __init__(self, age):
        self.age = age
```

### C#

```csharp
// Python: class User:
class User
{
    // Python: self.age
    public int Age { get; set; }
}
```

Пояснення
У C# поля часто приховують за властивостями.
Це дозволяє додати логіку, не змінюючи інтерфейс класу.

---

## Статичні члени класу

### Python

```python
class Math:
    pi = 3.14

print(Math.pi)
```

### C#

```csharp
// Python: class Math:
class MathUtils
{
    // Python: pi = 3.14
    public static double Pi = 3.14;
}

// Python: print(Math.pi)
Console.WriteLine(MathUtils.Pi);
```

Пояснення
`static` означає, що член належить класу, а не обʼєкту.
У Python це неявно. У C# завжди явно.

---

## Наслідування

### Python

```python
class Animal:
    def speak(self):
        print("sound")

class Dog(Animal):
    def speak(self):
        print("woof")
```

### C#

```csharp
// Python: class Animal:
class Animal
{
    // Python: def speak(self):
    public virtual void Speak()
    {
        // Python: print("sound")
        Console.WriteLine("sound");
    }
}

// Python: class Dog(Animal):
class Dog : Animal
{
    // Python: def speak(self):
    public override void Speak()
    {
        // Python: print("woof")
        Console.WriteLine("woof");
    }
}
```

Пояснення
У C# потрібно явно сказати:

* що метод можна перевизначати `virtual`
* що метод перевизначається `override`

Python робить це автоматично.

---

## Ключова різниця мислення

Python:

* клас це гнучка структура
* поля можуть зʼявлятися динамічно
* мінімум обмежень

C#:

* клас це строгий контракт
* всі поля і методи відомі наперед
* компілятор гарантує коректність

Python дозволяє імпровізацію.
C# змушує проєктувати.

---
## Завдання 4. Клас

### Мета  
Закріпити:
- створення класів
- поля та конструктор
- методи класу
- створення обʼєктів

### Умова

Створи клас `User`, який:

1) Має поля:
   - `Name` типу `string`
   - `Age` типу `int`

2) Має конструктор, який приймає:
   - імʼя
   - вік

3) Має метод `PrintInfo()`, який виводить у консоль:  
   `Name: <name>, Age: <age>`

Після цього в `Main`:

1) Зчитай імʼя та вік користувача з клавіатури  
2) Створи обʼєкт класу `User`  
3) Виклич метод `PrintInfo()`


## Головне резюме

Python класи зручні для швидкої розробки.
C# класи створені для великих систем, командної роботи і довгого життя коду.

Тепер ти бачив:

* введення і виведення
* типізацію
* умови
* цикли
* функції
* класи

