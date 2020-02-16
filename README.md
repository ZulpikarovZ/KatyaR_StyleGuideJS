# JavaScript StyleGuide
## Содержание
1. [Глобальные переменные](#Глобальные-переменные)
2. [Локальные переменные](#Локальные-переменные)
3. [Объекты](#Объекты)
4. [Преобразование типов](#Преобразование-типов)
5. [Оператор сравнения](#Оператор-сравнения)
6. [Параметры по умолчанию](#Параметры-по-умолчанию)
7. [Расположение скриптов](#Расположение-скриптов)
8. [Комментарии](#Комментарии)
9. [Точка с запятой](#Точка-с-запятой)
10. [Проверка кода](#Проверка-кода)
---
## Глобальные переменные
Избегайте глобальных переменных, сведите их использование к минимуму. Это касается всех типов данных, объектов и функций. Глобальные переменные и функции могут быть перезаписаны другими сценариями. Вместо этого пользуйтесь локальными переменными и замыканиями.
[⬆ наверх](#Содержание)
---
## Локальные переменные
Объявляйте локальные переменные в верхней части скрипта или функции.
Это позволяет:
* сделать код более чистым;
* обеспечить единое место для поиска локальных переменных;
* избежать совпадения имен с глобальными переменными;
* избежать повторного объявления переменных.
Инициализируйте объявленные переменные. Это позволяет избежать непределенных значений переменных.
```js
var firstName = "",
lastName = "",
age = 0,
experience = [],
property = {};
```
[⬆ наверх](#Содержание)
---
## Объекты
Не используйте `new` для инициализации объекта.
``` js
var x1 = {};           // вместо new Object()
var x2 = "";           // вместо new String()
var x3 = 0;            // вместо new Number()
var x4 = false;        // вместо new Boolean()
var x5 = [];           // вместо new Array()
var x6 = /()/;         // вместо new Regexp()
var x7 = function(){}; // вместо new Function()
```
[⬆ наверх](#Содержание)
---
## Преобразование типов
Остерегайтесь автоматического преобразования типов
```js
var x = "Строка";     // переменная x типа string
x = 5;               // меняет тип на number
```
[⬆ наверх](#Содержание)
---
## Операторы сравнения
Оператор `==` преобразует значения в значения одинакового типа перед сравнением.
Оператор `===` сравнивает типы и значения.
```js
0 == "";        // true
1 == "1";       // true
1 == true;      // true

0 === "";       // false
1 === "1";      // false
1 === true;     // false
```
[⬆ наверх](#Содержание)
---
## Параметры по умолчанию
Если при вызове функции был пропущен аргумент, значение пропущенного аргумента устанавливается в `underfined`. Это может повлиять на исполнение кода и его результат. Хорошим тоном считается задавать дефолтные значения параметрам функции.
```js
function myFunction(x, y) {
  if (y === undefined) {
    y = 0;
  }
}
```
[⬆ наверх](#Содержание)
---
## Расположение скриптов
Располагайте скрипты в конце HTML-страницы. Первичная задача разработчика - сделать загрузку страницы как можно более быстрой. Исполнение скрипта может замедлить загрузку страницы.
```html
<p>Контакты: example@mail.ru</p>
<script type="text/javascript" src="path/to/file.js"></script>
<script type="text/javascript" src="path/to/anotherFile.js"></script>
</body>
</html>
```
[⬆ наверх](#Содержание)
---
## Комментарии
Добавляйте комментарии к важным участкам кода. Вам будет легче его понять, если вернуться к коду через какое-то время или если кода много. К тому же, вашим коллегам будет легче разобраться в нем, если вы работаете в команде. Но не переусердствуйте! Избыточные комментарии мешают чтению кода.
```js
// проверка на совершеннолетие
const checkAge = (age) => {
  return age > 18;
}
```
[⬆ наверх](#Содержание)
---
## Точка с запятой
Всегда используйте точку с запятой. Большинство браузеров верно интерпретирует код без завершающей точки с запятой, но с отдельными браузерами могут возникнуть проблемы, и будет трудно отловить ошибку.
```js
var someItem = 'some string';
function doSomething() {
  return 'something';
}
```
[⬆ наверх](#Содержание)
---
## Проверка кода
Проверяйте свой код общедоступными отладчиками, например, [JSLint](https://www.jslint.com/). Это поможет избежать части ошибок. Прежде чем опубликовать скрипт, выполните его проверку.
