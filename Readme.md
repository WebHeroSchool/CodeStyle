# Стиль кода JavaScript

#### 1. Фигурные скобки.
Фигурные скобки пишутся в так называемом «египетском» стиле. Перед открывающей скобкой должен быть пробел.

``` js
// good
if (...) {
//to do
}
```

Если запись кода однострочная, фигурные скобки не нужны.
Начинаюшие программситы иногда добавляют лишние фигурные скобки, которые ухудшают читаемость кода.

``` js
// bad
f (n < 0) {console.log(`n меньше 0`);}
```

Никогда не разделяйте строки без фигурных скобок.

``` js
// bad
if (n < 0)
  console.log(`n меньше 0`);
```

Можно писать короткие строки в одну.

``` js
// good
if (n < 0) alert(`Степень ${n} не поддерживается`);
```

Самый лучший вариант:

``` js
// good
if (n < 0) {
  alert(`Степень ${n} не поддерживается`);
}
```

#### 2. Не использовать var
Объявляйте все переменные с помощью const или let. По умолчанию используется const, за исключением случаев, когда нужно переназначить переменную. Ключевое слово var не должно использоваться.

``` js
// bad
var five = 5;
function toCube(num) {
    var result = num * num * num;
    return result;
}
var fiveInCube = toCube(five);
// good
const five = 5;
function toCube(num) {
    let result = num * num * num;
    return result;
}
let fiveInCube = toCube(five);
```

#### 3. Точка с запятой
Точки с запятой должны присутствовать после каждого выражения, даже если их, казалось бы, можно пропустить.

``` js
// bad
alert('Hi')
let person = {}
person.name = 'Sergey'
// good
alert('Hi');
let person = {};
person.name = 'Sergey';
```

#### 4. Используйте одинарные, а не двойные кавычки
Обычные строковые литералы ограничиваются одинарной кавычкой (‘), а не двойной (").

Совет: если строка содержит символ одинарной кавычки, подумайте об использовании строки шаблона, чтобы не пришлось избавляться от цитаты.

``` js
// bad
let directive = "No identification of self or mission."
// bad
let saying = 'Say it ain\u0027t so.';
// good
let directive = 'No identification of self or mission.';
// good
let saying = `Say it ain't so`;
```

#### 5. Для создания объекта используйте фигурные скобки.
Не создавайте объекты через конструктор new Object.

``` js
// bad
const item = new Object();
// good
const item = {};
```

#### 6. Зарезервированные слова.
Не используйте зарезервированные слова в качестве ключей объектов.

``` js
// bad
let superman = {
  default: { clark: 'kent' },
  private: true
};
// good
let superman = {
  defaults: { clark: 'kent' },
  hidden: true
};
```
#### 7. Менять стили через css, а не с помощью js.
Вместо того, чтобы менять стили элементов через DOM
лучше создать класс с нужными стилями в файле style.css
и в коде javascript добавилять нужный класс со стилями 
элементу

``` js
// bad
let button = document.getElementById('main-button');
button.style.padding = '20px';
button.style.background = 'red';
button.style.color = 'white';
button.style.fontWeight = 'bold';
// good
let button = document.getElementById('main-button');
button.className.add('red');
};
```

#### 8. Используйте === Сравнение
Оператор == сравнения всегда преобразует (в соответствующие типы) перед сравнением. пример

``` js
// bad
0 == "";        // true
1 == "1";       // true
1 == true;      // true
// good
0 === "";       // false
1 === "1";      // false
1 === true;     // false
```
#### 9. Снижение числа глобальных переменных.
Снижением количества глобальных переменных к минимуму, вы значительно уменьшаете шансы нежелательного взаимодействия с другими приложениями, виджетами или библиотеками.
``` js
// bad
let name = 'Jeffrey';  
let lastName = 'Way';  
  
function doSomething() {...}  
  
console.log(name);
// good
let DudeNameSpace = {  
   name : 'Jeffrey',  
   lastName : 'Way',  
   doSomething : function() {...}  
}  
console.log(DudeNameSpace.name);
```

#### 10. Используйте понятные имена переменных и функций.
Когда при написании кода используют понятные, описательные имена функций и переменных, его гораздо легче понимать и читать. Не стремитесь к минимализму при названии переменных. Важно использовать понятные имена переменных, отражающие их смысл.

``` js
// bad
function swa(a) {
let x = a.reduse((x, y) => x + y);
return s / a.lenght
}
// good
fuction getArray (array) {
    let smthArray = ['cat', 'dog']
    console.log(smthArray)
}
```