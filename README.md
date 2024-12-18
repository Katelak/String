# String в JavaScript

## Описание
`String` — это встроенный объект в JavaScript, который используется для работы со строками. Строки представляют собой набор символов, заключённых в кавычки (одинарные `'`, двойные `"` или обратные `` ` ``). Строки неизменяемы, что означает, что их содержимое нельзя изменить после создания.

Пример создания строк:

```javascript
const singleQuote = 'Привет';
const doubleQuote = "Мир";
const templateLiteral = `Привет, ${doubleQuote}`; // Привет, Мир
```

---

## Создание строк

1. **С помощью литералов**
   
   ```javascript
   const str = 'Пример строки';
   ```

2. **С помощью конструктора**
   
   ```javascript
   const str = new String('Пример строки');
   ```

> **Важно:** Использование конструктора `String` создаёт объект-обёртку, а не примитивную строку.

---

## Основные методы и свойства строк

### Свойства:

- `length`: Возвращает длину строки.
  
  ```javascript
  const str = 'Пример';
  console.log(str.length); // 6
  ```

### Методы:

#### 1. Изменение регистра:
- `toUpperCase()` — переводит все символы строки в верхний регистр.
  
  ```javascript
  console.log('пример'.toUpperCase()); // ПРИМЕР
  ```

- `toLowerCase()` — переводит все символы строки в нижний регистр.
  
  ```javascript
  console.log('ПРИМЕР'.toLowerCase()); // пример
  ```

#### 2. Работа с подстроками:
- `substring(start, end)` — возвращает подстроку от индекса `start` до `end` (не включая `end`).
  
  ```javascript
  console.log('Пример'.substring(0, 3)); // При
  ```

- `slice(start, end)` — аналогично `substring`, но поддерживает отрицательные индексы.
  
  ```javascript
  console.log('Пример'.slice(-3)); // мер
  ```

- `substr(start, length)` — возвращает подстроку длиной `length`, начиная с индекса `start`.
  
  ```javascript
  console.log('Пример'.substr(0, 3)); // При
  ```

#### 3. Поиск подстрок:
- `indexOf(searchValue)` — возвращает индекс первого вхождения `searchValue` или `-1`, если подстрока не найдена.
  
  ```javascript
  console.log('Пример строки'.indexOf('строки')); // 7
  ```

- `includes(searchValue)` — проверяет, содержится ли подстрока `searchValue`.
  
  ```javascript
  console.log('Пример строки'.includes('Пример')); // true
  ```

#### 4. Разделение и объединение:
- `split(separator)` — разбивает строку на массив подстрок по указанному разделителю.
  
  ```javascript
  console.log('a,b,c'.split(',')); // ['a', 'b', 'c']
  ```

- `concat(...strings)` — объединяет строки.
  
  ```javascript
  console.log('Привет'.concat(', ', 'Мир!')); // Привет, Мир!
  ```

#### 5. Удаление пробелов:
- `trim()` — удаляет пробелы с начала и конца строки.
  
  ```javascript
  console.log('  Пример  '.trim()); // Пример
  ```

#### 6. Замена:
- `replace(searchValue, newValue)` — заменяет первое вхождение `searchValue` на `newValue`.
  
  ```javascript
  console.log('Привет, Мир!'.replace('Мир', 'JavaScript')); // Привет, JavaScript!
  ```

- `replaceAll(searchValue, newValue)` — заменяет все вхождения `searchValue` на `newValue` (ES2021).
  
  ```javascript
  console.log('aaa'.replaceAll('a', 'b')); // bbb
  ```

#### 7. Повторение строки:
- `repeat(count)` — возвращает строку, повторённую `count` раз.
  
  ```javascript
  console.log('Привет '.repeat(3)); // Привет Привет Привет
  ```

---

## Шаблонные строки

Шаблонные строки используют обратные кавычки (`` ` ``) и позволяют встраивать переменные и выражения с помощью синтаксиса `${expression}`.

```javascript
const name = 'Иван';
const age = 25;
console.log(`Привет, меня зовут ${name}, мне ${age} лет.`);
```

---

## Полезные советы

1. **Проверка на пустую строку:**
   ```javascript
   const isEmpty = (str) => str.length === 0;
   console.log(isEmpty('')); // true
   ```

2. **Реверс строки:**
   ```javascript
   const reverseString = (str) => str.split('').reverse().join('');
   console.log(reverseString('Пример')); // ремирП
   ```

3. **Сравнение строк (регистронезависимое):**
   ```javascript
   const equalsIgnoreCase = (str1, str2) => str1.toLowerCase() === str2.toLowerCase();
   console.log(equalsIgnoreCase('Привет', 'привет')); // true
   ```

---

## Заключение
`String` — это мощный и гибкий инструмент для работы со строками в JavaScript. Знание методов и особенностей строкового объекта позволяет эффективно обрабатывать текстовые данные.

