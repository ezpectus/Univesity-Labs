# 🧪 Lab01: Scalar Types, References & Type Analysis

## ✅ Task 1: Scalar vs Reference

```csharp
Console.WriteLine("Task 1: Scalar types vs References");

int a = 5; // Присваиваем переменной a значение 5

int IncNum(int num) => num + 1; // Работаем с копией числа (значимый тип)

int IncObj(MyNum obj) => obj.n + 1; // Работаем с объектом по ссылке (reference type)

var b = IncObj(new MyNum { n = a }); // Создаём объект с полем n = a
var c = IncNum(a); // Передаём просто число

Console.WriteLine($"b: {b}, c: {c}");
Console.WriteLine($"a: {a}"); // Значение a не изменилось — передавалось по значению

class MyNum { public int n; } // Класс для демонстрации ссылочного типа

```

## ✅ Task 2: Type Counting
```csharp
Console.WriteLine("\nTask 2: Type Analysis\n");

object[] arr = {
    true, "hello", 5, 12, -200, false, "word", "word", "hello",
    4, 1, false, true, true, -200, 5, 5, 1, 1, 1, 1
}; // Массив с элементами разных типов

var freq = new Dictionary<string, int>(); // Словарь: тип → количество

foreach (var elem in arr) {
    string type = elem.GetType().Name;
    if (!freq.ContainsKey(type)) freq[type] = 1; // Если тип ещё не встречался — добавляем
    else freq[type]++; // Иначе увеличиваем счётчик
}

foreach (var kv in freq)
    Console.WriteLine($"{kv.Key}: {kv.Value}"); // Выводим тип и его количество

```



---
