## Wow

А ты знал, почему используют букву i во время перебора порядковых номеров элементов в массиве?  
i - это index. Index - это номер элемента.  

## Классический цикл

```js
var array = ["илья", "глеб", "алекс"];

for(var i=0; i<array.length; i++){
  var element = array[i];
  console.log( i , "|" , element );
}
```

Вывод:
```
-> 0 | илья
-> 1 | глеб
-> 2 | алекс
```

## Цикл с перебором индекса (0,1,2, ...)
Делается с помощью оператора **in** .  
Он сам определяет размер массива, поэтому не обязательно писать i<array.length

```js
var array = ["илья", "глеб", "алекс"];

for(var i in array){
  var element = array[i];
  console.log( i , "|" , element );
}
```

Вывод:
```
-> 0 | илья
-> 1 | глеб
-> 2 | алекс
```

## Цикл с перебором элементов массива ("илья", "глеб", "алекс", ...)
Делается с помощью оператора **of** .  
Он сам определяет размер массива, поэтому не обязательно писать i<array.length

Этот вариант не даст тебе возможности узнать порядковый номер, но зато легко и без лишних строк **даст сам перебираемый элемент.**

```js
var array = ["илья", "глеб", "алекс"];

for(var element of array){
  console.log( element );
}
```

Вывод:
```
-> илья
-> глеб
-> алекс
```

## Сверхбыстрые решения

### Фильтрация: .filter()
Программистам всегда лень писать много кода, поэтому появилось это чудо.  

Задача: нужно быстро найти количество объектов, где значение **wow** является **true**  


Прогеры придумали штуку, как **.filter()** , чтобы не писать 10 строк однотипного кода каждый раз.  

Пример:
```js
var array = [
  {name: "глеб", age: 34, wow: false},
  {name: "илья", age: 17, wow: false},
  {name: "алекс", age: 33, wow: true},
  {name: "кирилл", age: 53, wow: false},
  {name: "олег", age: 14, wow: true},
  {name: "никита", age: 23, wow: true},
  {name: "сергей", age: 12, wow: false},
]

// Формируем новый массив, который состоит исключительно из элементов с wow: true
// ТОБИШЬ ФИЛЬТРУЕМ
var wowed = array.filter(x=> x.wow==true );

// или еще короче
var wowed = array.filter(x=> x.wow ); // x.wow означает, что x.wow "существует", то есть все-что угодно кроме false

// а теперь ищем там же пиздюков до 18 лет
var young = array.filter(x=> x.age<18 );

// а теперь найдем пиздюков, которые "wow"
var young_wowed = array.filter(x=> x.age<18 ).filter(x=> x.wow );
//                            фильтр по возрасту, а потом по wow
// или короче
var young_wowed = array.filter(x=> x.age<18 && x.wow );
```

В итоге в **wowed**:
```js
[
  {name: "алекс", age: 33, wow: true},
  {name: "олег", age: 14, wow: true},
  {name: "никита", age: 23, wow: true}
]
```

В итоге в **young**:
```js
[
  {name: "илья", age: 17, wow: false},
  {name: "олег", age: 14, wow: true},
  {name: "сергей", age: 12, wow: false}
]
```

В итоге в **young_wowed**:
```js
[
  {name: "олег", age: 14, wow: true}
]
```
