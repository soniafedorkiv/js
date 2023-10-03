# Loops-Functions

1. Написати функцію `compact()` яка має приймати на вхід масив, а на вихід має повертати значення нового масиву без повторень.
```js
const arr = [5, 3, 4, 5,6,7,3];
const arr2 = compact(arr);
console.log(arr2) ; // [5,3,4,6,7]
function compact(Arr){
const uniqueArray = [];
 for (const item of arr) {
    if (!uniqueArray.includes(item)) {
      uniqueArray.push(item);
    }
  }

  return uniqueArray;
}
```
2. Написати функцію `createArray(start, end)`, яка приймає на вхід 2 параметри: **початкове значення** та **кінцеве значення**, а на виході отримує масив із діапазоном цих значень (реалізувати достатньо лише із числовими значеннями).
```js
function createArray(start, end) {
  if (start > end) {
    console.log("Error");
    return [];
  }
const startValue = 2;
const endValue = 9;
const newArray = createArray(startValue, endValue);
console.log(newArray); // [2, 3, 4, 5, 6, 7, 8, 9]
```
3. Задані цілі числа **a** і **b** (**a < b**). Виведіть усі цілі числа від **a** до **b** включно, при цьому a виводится один раз, число **а+1** - два рази і т.д.

4. Напишіть функцію `randArray(k)`, яка заповнюватиме масив `k` випадковими цілими числами. Випадкові числа генеруються із діапазону **1-500**.
```js
function randArray(k) {
  const result = [];
  for (let i = 0; i < k; i++) {
    const randomNumber = Math.floor(Math.random() * 500) + 1;
    result.push(randomNumber);
  }
  return result;
}

const randomNumbers = randArray(5);
console.log(randomNumbers);
randArray(5);  // [399,310,232,379,40]
```

5. Є масив `arr`, який може містити підмасиви, написати функцію `showByTypes` яка виведе у консоль масиви які складаються із примітивних даних початкового масиву і усіх вкладених масивів, але одного типу даних (не приводити тип **String** в **Number** навіть, якщо там лише число).
```js
let  arr = [5, "Limit", 12, "a", "3", 99, 2, [2, 4, 3, "33", "a", "text"], "strong", "broun"];
showByTypes(arr);
 /* 
[5, 12, 99, 2, 2, 4, 3]
["Limit", "a", "3", "33", "a", "text", "strong", "broun"]
*/
```

6. Напишіть функцію `calc(a, b, op)`, яка виконує над числами `a` і `b` одну із арифметичних операцій та повертає її результат. Вид операції визначається цілим числом `op`:
**1** – _віднімання_,
**2** – _добуток_,
**3** – _ділення_,
**інші значення** – _додавання_.
```js
function calc(a, b, op) {
  let result;

  switch (op) {
    case 1:
      result = a - b;
      break;
    case 2:
      result = a * b;
      break;
    case 3:
      if (b !== 0) {
        result = a / b;
      } else {
        result = "error";
      }
      break;
    default:
      result = a + b;
  }

  return result;
}

console.log(calc(5, 2, 2)) //10
```

7. Напишіть функцію `findUnique(arr)`, яка приймає масив `arr` і перевіряє на унікальність його елементи. Якщо всі елементи масиву унікальні (не мають дублів), то функція поверне **true**, інакше - **false**.
```js
function findUnique(arr) {
  
  const count = {};

  
  for (const element of arr) {
   
    if (count[element]) {
      return false;
    }
    
    count[element] = 1;
  }

  
  return true;
}
findUnique([1, 2, 3, 5, 3]);  // => false
findUnique([1, 2, 3, 5, 11]); // => true
```

⭐⭐⭐

(Ускладнене. Задача не оцінюється. Для тих, кому хочеться поробити ще щось)

Створити функцію `create()`, яка приймає один аргумент у вигляді рядка. Ця функція повертає анонімну функцію, яка перевіряє чи переданий в неї аргумент збігається з аргументом зовнішньої функції.
```js
const tom = create("pass_for_Tom");
tom("pass_for_Tom"); //повертає true 
tom("pass_for_tom"); //повертає false
```
